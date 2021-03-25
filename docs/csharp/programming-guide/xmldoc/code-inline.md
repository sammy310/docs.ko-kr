---
title: <c> - C# 프로그래밍 가이드
description: XML <c> 태그에 대해 알아봅니다. 이 태그는 설명의 한 줄 텍스트를 코드로 표시하고, <code> indicates multiple lines.
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: fc445c7245287c3835543e4bbe4b3b46ec46fd35
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478695"
---
# <a name="c-c-programming-guide"></a>\<c>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<c>text</c>
```

## <a name="parameters"></a>매개 변수

- `text`

  코드로 표시하려는 텍스트입니다.

## <a name="remarks"></a>설명

`<c>` 태그를 사용하면 설명 내의 텍스트를 코드로 표시해야 함을 지정할 수 있습니다. 여러 줄을 코드로 지정하려면 [\<code>](./code.md)를 사용합니다.

[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
