---
title: <typeparam> - C# 프로그래밍 가이드
description: XML <typeparam> 태그에 대해 알아봅니다. 이 태그는 제네릭 형식 또는 메서드 선언의 주석에서 형식 매개 변수를 설명하는 데 사용됩니다.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 1b9d5d30c1a507e3bb7938ee0c036cdac3ef2f90
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477684"
---
# <a name="typeparam-c-programming-guide"></a>\<typeparam>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a>매개 변수

- `name`

  형식 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.

- `description`

  형식 매개 변수에 대한 설명입니다.

## <a name="remarks"></a>설명

`<typeparam>` 태그는 제네릭 형식 또는 메서드 선언의 주석에서 형식 매개 변수를 설명하는 데 사용해야 합니다. 제네릭 형식 또는 메서드의 각 형식 매개 변수에 대한 태그를 추가합니다.

자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.

`<typeparam>` 태그에 대한 텍스트는 IntelliSense와 [개체 브라우저 창](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)의 코드 주석 웹 보고서에 표시됩니다.

[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../../language-reference/index.md)
- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
