---
title: <para> - C# 프로그래밍 가이드
description: XML <para> 태그에 대해 알아봅니다. 이 태그를 사용하면 다음과 같은 다른 태그의 텍스트에 구조체를 추가할 수 있습니다. <summary>, <remarks>또는 <returns>.
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 5cb1c22dceae7a45a47fcb8807303d11e1220935
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478002"
---
# <a name="para-c-programming-guide"></a>\<para>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<para>content</para>
```

## <a name="parameters"></a>매개 변수

- `content`

  단락의 텍스트입니다.

## <a name="remarks"></a>설명

`<para>` 태그는 [\<summary>](./summary.md), [\<remarks>](./remarks.md) 또는 [\<returns>](./returns.md) 같은 태그 내에 사용되어 텍스트에 구조를 추가할 수 있게 합니다.

[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

`<para>` 사용 예제는 [\<summary>](./summary.md)를 참조하세요.

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
