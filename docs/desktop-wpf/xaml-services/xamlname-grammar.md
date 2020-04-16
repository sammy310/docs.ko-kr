---
title: XamlName 문법
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 2fc74990b15caaa9b58e6eea5b0212ea22505674
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433051"
---
# <a name="xamlname-grammar"></a>XamlName 문법

XamlName 문법은 XAML 언어 사양 [MS-XAML]에 정의된 특정 문법으로, 편의를 위해 여기에 재현됩니다.

## <a name="from-the-xaml-specification"></a>XAML 사양에서

[MS-XAML] 사양은 형식 및 속성에 사용되는 법적 기호 식별자 집합을 식별하기 위해 문법 XamlName을 정의합니다.

XamlName 형식의 문자열 값은 다음 문법을 준수해야 합니다.

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

유니코드 문자 데이터베이스에 정의된 다음과 같은 일반 범주 값을 가정합니다.

| 유니코드 범주   | 설명                   |
|--------------------|-------------------------------|
| 루어                 | 문자, 대문자             |
| Ll                 | 문자, 소문자             |
| Lt                 | 문자, 제목 스타일             |
| Lm                 | 문자, 한정자              |
| Lo                 | 문자, 기타                 |
| Mn                 | 마크, 간격이 없는 경우             |
| Mc                 | 표시, 공백 조합       |
| Nd                 | 번호, 소수점               |
| Nl                 | 숫자, 문자                |

XAML은 속성 및 이벤트 정규화된 참조및 연결된 멤버에 사용되는 두 번째 문법인 DottedXamlName을 정의합니다. 자세한 내용은 및 <xref:System.Windows.DependencyProperty> [XAML 개요(WPF)를](../fundamentals/xaml.md)참조하십시오.

DottedXamlName 형식의 문자열 값은 다음 문법을 준수해야 합니다.

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>설명

전체 사양은 [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))을 참조하십시오.
