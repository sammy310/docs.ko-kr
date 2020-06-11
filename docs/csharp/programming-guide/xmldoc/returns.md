---
title: <returns> - C# 프로그래밍 가이드
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 7bc950a8d89a3ac2b5c3b7a68e05c7778e97f85c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287235"
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
