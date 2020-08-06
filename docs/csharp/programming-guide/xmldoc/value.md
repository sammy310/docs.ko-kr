---
title: <value> - C# 프로그래밍 가이드
description: XML <value> 태그에 대해 알아봅니다. 이 태그를 통해 속성이 나타내는 값을 설명할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380776"
---
# <a name="value-c-programming-guide"></a>\<value>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<value>property-description</value>
```

## <a name="parameters"></a>매개 변수

- `property-description`

  속성에 대한 설명입니다.

## <a name="remarks"></a>설명

`<value>` 태그를 사용하면 속성이 나타내는 값을 설명할 수 있습니다. Visual Studio .NET 개발 환경에서 코드 마법사를 통해 속성을 추가하면 새 속성에 대해 [\<summary>](./summary.md) 태그가 추가됩니다. 그런 다음, `<value>` 태그를 수동으로 추가하여 속성이 나타내는 값을 설명해야 합니다.

[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
