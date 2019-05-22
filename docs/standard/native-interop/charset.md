---
title: 문자 집합 및 마샬링 - .NET
description: CharSet의 여러 값을 통해 .NET에서 데이터를 네이티브 코드로 마샬링하는 방식을 변경하는 방법을 알아봅니다.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: c50c58ad639b1efb29c13e5124fe3c32e8af96fc
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063332"
---
# <a name="charsets-and-marshaling"></a>문자 집합 및 마샬링

`char` 값, `string` 개체 및 `System.Text.StringBuilder` 개체가 마샬링되는 방식은 P/Invoke 또는 구조체 중 하나의 `CharSet` 필드 값에 따라 다릅니다. P/Invoke를 선언할 때 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드를 설정하여 P/Invoke의 `CharSet`를 설정할 수 있습니다. 구조체의 `CharSet`를 설정하려면 구조체 선언의 <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> 필드를 설정합니다. 이러한 특성 필드가 설정되지 않은 경우 사용할 `CharSet`는 언어 컴파일러에서 결정합니다. C# 및 VB에서는 기본적으로 <xref:System.Runtime.InteropServices.CharSet.Ansi> 문자 집합을 사용합니다.

다음 표에서는 각 문자 집합과 해당 문자 집합으로 마샬링할 때 문자 또는 문자열을 나타내는 방법 간의 매핑을 보여 줍니다.

| `CharSet` 값 | Windows            | Unix에서 .NET Core 2.2 및 그 이전 | Unix에서 .NET core 3.0 이상 및 Mono |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char`(ANSI)      | `char`(UTF-8)                    | `char`(UTF-8)                           |
| 유니코드(Unicode)         | `wchar_t`(UTF-16) | `char16_t`(UTF-16)               | `char16_t`(UTF-16)                      |
| 자동            | `wchar_t`(UTF-16) | `char16_t`(UTF-16)               | `char`(UTF-8)                           |

문자 집합을 선택할 때 네이티브 표현에 필요한 표현을 알고 있어야 합니다.
