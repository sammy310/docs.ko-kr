---
title: <exception> - C# 프로그래밍 가이드
description: XML <exception> 태그에 대해 알아봅니다. 이 태그는 throw할 수 있는 예외를 지정하는 데 사용되며 메서드, 속성, 이벤트 및 인덱서에 적용될 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 37d119e3cde115104d149d8f35b8937efddd70d4
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103479105"
---
# <a name="exception-c-programming-guide"></a>\<exception>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a>매개 변수

- cref = " `member`"

  현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조입니다. 컴파일러는 지정된 예외가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다. `member`는 큰따옴표(" ")로 묶어야 합니다.

  제네릭 형식을 참조하도록 `member` 형식을 지정하는 방법에 대한 자세한 내용은 [XML 파일 처리](processing-the-xml-file.md)를 참조하세요.

- `description`

  예외에 대한 설명입니다.

## <a name="remarks"></a>설명

`<exception>` 태그를 사용하면 throw할 수 있는 예외를 지정할 수 있습니다. 이 태그는 메서드, 속성, 이벤트 및 인덱서에 대한 정의에 적용할 수 있습니다.

[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.

예외 처리에 대한 자세한 내용은 [예외 및 예외 처리](../exceptions/index.md)를 참조하세요.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](recommended-tags-for-documentation-comments.md)
