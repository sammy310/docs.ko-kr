---
title: <remarks> - C# 프로그래밍 가이드
description: XML <remarks> 태그에 대해 알아봅니다. 이 태그는 형식에 대한 정보를 추가하여 다음으로 지정된 정보를 보완하기 위해 사용됩니다. <summary>.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381504"
---
# <a name="remarks-c-programming-guide"></a>\<remarks>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a>매개 변수

- `Description`

  멤버에 대한 설명입니다.

## <a name="remarks"></a>설명

`<remarks>` 태그는 형식에 대한 정보를 추가하여 [\<summary>](./summary.md)로 지정된 정보를 보완하기 위해 사용됩니다. 이 정보는 개체 브라우저 창에 표시됩니다.

[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
