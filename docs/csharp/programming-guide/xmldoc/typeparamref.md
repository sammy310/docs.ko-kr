---
title: <typeparamref> - C# 프로그래밍 가이드
description: XML <typeparamref> 태그에 대해 알아봅니다. 이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 1bb9a73f4122f3b9d521565a7172a9b8f75f7a98
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477672"
---
# <a name="typeparamref-c-programming-guide"></a>\<typeparamref>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a>매개 변수

- `name`

  형식 매개 변수의 이름입니다. 이름을 큰따옴표(“ ”)로 묶습니다.

## <a name="remarks"></a>설명

제네릭 형식 및 메서드의 형식 매개 변수에 대한 자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.

이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.

[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
