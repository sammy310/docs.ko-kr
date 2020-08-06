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
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381400"
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

[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
