#aor
### Block Statement
>[!note]
>#### 블록문
>
>>Mark-up 코드에 영향을 주는 명령문

#### `#if`

- `#if` 해시태그를 사용하여 조건문 입력이 가능하다.

사용법:
```javascript
<script>
  let name = 'Yoon';
  let description = 'Active Person';
  let done = true;
</script>

{#if done} // <= true일 경우에만 콘텐츠 렌더링
<ContactCard userName={name} description={description} />
{:else done === false} // <= in-between 문일 경우 콜론을 붙이며 이어나가면 된다.
<p>Input is invalid</p>
{/if}
```

#### `#each`

- `#each` 해시태그를 사용하여 반복문 입력이 가능하다.
- 아래의 방식처럼 `{else}`를 이용하면, 배열이 비어있는 경우를 특정해서 보여줄 수 있다.

사용법: 
```html
<script>
    import ContactCard from "./ContactCard.svelte";
  
    let name = 'Yoon';
    let description = 'Active Person';
    let title = "Park";
    let image = "http://naver.com";
    let formState = "empty";
  
    let createdContact = [];
  
    function addContact() {
        createdContact = [
            ...createdContact,
            {
                name: name,
                jobTitle: title,
                imgUrl: image,
                desc: description,
            }
        ];
        formState = "done";
    }
</script>

<button on:click={addContact}>Add Contact Card</button>

{#each createdContact as contact, index} <!-- index를 걸어줄 수 있다. -->
    <h2># {index}</h2>
    <ContactCard
        userName={contact.name}
        jobTitle={contact.jobTitle}
        description={contact.desc}
        userImage={contact.imgUrl}
    />
  
{:else}
    <p>Please start adding some contacts, we found none!</p>

{/each}
```

>[!bug]
>>Svelte는 목록에서의 개별 요소들을 따로 구분짓지 않아
>데이터가 잘못된 요소에 연결될 수 있다.
>
>>Svelte의 기본동작은 목록을 끝에서부터 변경하는 것이기 때문에, 첫번째 요소를 삭제 및 변경을 하면, 데이터가 잘못된 요소에 연결될 수 있다.
>
>>이를 위해서 Svelte가 데이터를 DOM Mark-up 요소에 연결하는데 도움이 되는 각 고유 식별자를 입력하면 잘못된 요소에 연결되는 것을 막을 수 있다.

>[!important]
>>하단과 같이 객체에 `id: Math.random()` 값을 통해 고유 식별 값을 할당하고 해당 id를 컴포넌트에 입력하면 잘못된 요소에 연결되는 것을 막을 수 있다.
>
>>추가적으로 고유 식별 값을 할당하면, 선택해야 하는 요소의 정확한 위치를 알 수 있기 때문에, 성능 면에서도 효율적이다.

해결법 : 
```html
<script>
createdContacts = [...createdContact, 
	{
		id: Math.random(),
		name: name,
		jobTitle: title,
		imgUrl: image,
		desc: description
	}
];
</script>

{#each createdContact as contact, index (contact.id)}
    <h2># {index}</h2>
    <ContactCard
        userName={contact.name}
        jobTitle={contact.jobTitle}
        description={contact.desc}
        userImage={contact.imgUrl}
    />
  
{:else}
    <p>Please start adding some contacts, we found none!</p>
{/each}
```

### [Svelte](../../../Dev-Index/Svelte.md) index로 돌아가기