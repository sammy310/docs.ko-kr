---
title: <returns> - C# 프로그래밍 가이드
description: XML <returns> 태그에 대해 알아봅니다. 이 태그는 메서드 선언의 주석에서 반환 값을 설명하는 데 사용됩니다.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 6a098208a51ca31fe2278b7c696deb15a13f8e1e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477814"
---
# <a name="returns-c-programming-guide"></a>\<returns>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<returns>description</returns>
```

## <a name="parameters"></a>매개 변수

- `description`

  반환 값에 대한 설명입니다.

## <a name="remarks"></a>설명

`<returns>` 태그는 메서드 선언의 주석에서 반환 값을 설명하는 데 사용해야 합니다.

[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
