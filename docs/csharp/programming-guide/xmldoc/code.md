---
title: <code> - C# programming guide
description: XML <code> tag. This tag is used to indicate multiple lines of code, while <c> marks single-line text in a description as code.에 대해 알아봅니다.
ms.date: 07/20/2015
f1_keywords:
- code
- <code>
helpviewer_keywords:
- code XML tag
- <code> C# XML tag
ms.assetid: f235e3bc-a709-43cf-8a9f-bd57cabdf6da
ms.openlocfilehash: efc4314a634e3349fc5d7584b4c51130ff057e5b
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103479134"
---
# <a name="code-c-programming-guide"></a>\<code>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<code>content</code>
```

## <a name="parameters"></a>매개 변수

- `content`

  코드로 표시할 텍스트입니다.

## <a name="remarks"></a>설명

`<code>` 태그는 여러 코드 줄을 나타내는 데 사용됩니다. 설명 내의 한 줄 텍스트가 코드로 표시되도록 지정하려면 [\<c>](./code-inline.md)를 사용합니다.

[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

`<code>` 태그를 사용하는 방법에 대한 예제는 [\<example>](./example.md) 문서를 참조하세요.

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
