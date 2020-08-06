---
title: <list> - C# 프로그래밍 가이드
description: XML <list> 태그에 대해 알아봅니다. 이 태그는 'item' 블록을 사용하여 테이블 및 정의, 글머리 기호 또는 번호 매기기 목록을 만드는 데 사용됩니다.
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 361c2e6f343554a9b8519c3b2e41219b209e682d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381868"
---
# <a name="list-c-programming-guide"></a>\<list>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a>매개 변수

- `term`

  `description`에서 정의되는, 정의할 용어입니다.

- `description`

  글머리 기호 또는 번호 매기기 목록의 항목이나 `term`의 정의입니다.
  
## <a name="remarks"></a>설명

`<listheader>` 블록은 테이블 또는 정의 목록의 머리글 행을 정의하는 데 사용됩니다. 테이블을 정의할 때는 머리글에 용어 항목만 제공하면 됩니다.

목록의 각 항목은 `<item>` 블록을 사용하여 지정됩니다. 정의 목록을 만들 때는 `term`과 `description`을 모두 지정해야 합니다. 그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우 `description` 항목만 제공하면 됩니다.

목록 또는 테이블에 `<item>` 블록을 필요한 개수만큼 포함할 수 있습니다.

[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
