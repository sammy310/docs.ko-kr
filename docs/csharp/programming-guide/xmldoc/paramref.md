---
title: <paramref> - C# 프로그래밍 가이드
description: XML <paramref> 태그에 대해 알아봅니다. 이 태그는 코드의 단어가 매개 변수임을 나타내는 방법을 제공합니다.
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: e559a899aad7806bb7ccef32be49954fabed6a32
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477881"
---
# <a name="paramref-c-programming-guide"></a>\<paramref>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<paramref name="name"/>
```

## <a name="parameters"></a>매개 변수

- `name`

  참조할 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.

## <a name="remarks"></a>설명

`<paramref>` 태그를 사용하면 `<summary>` 또는 `<remarks>` 블록 등의 코드 주석에 포함된 단어가 매개 변수를 참조함을 나타낼 수 있습니다. XML 파일을 처리하여 굵게, 기울임꼴 글꼴 등의 고유한 방식으로 이 단어에 서식을 지정할 수 있습니다.

[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
