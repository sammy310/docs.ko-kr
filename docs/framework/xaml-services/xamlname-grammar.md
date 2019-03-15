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
ms.openlocfilehash: 642ca16142bdfe78a40ddf4e6a3a79ce6a8a4985
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58031598"
---
# <a name="xamlname-grammar"></a>XamlName 문법
XamlName 문법에는 편의 위해 여기에 재현 되어 있는 XAML 언어 사양 [MS-XAML]에 정의 된 특정 문법입니다.  
  
## <a name="from-the-xaml-specification"></a>XAML 사양에서  
 [MS XAML] 형식 및 속성에 사용 되는 올바른 기호 식별자 집합을 식별 하기 위해 XamlName 문법을 정의 합니다.  
  
 XamlName 다음 문법을 준수 해야 하는 형식의 값을 문자열:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 유니코드 문자 데이터베이스에 정의 된 대로 다음과 같은 일반 범주 값을 가정 하는  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 XAML DottedXamlName 속성에 사용 되는 두 번째 문법에 정의 및 이벤트 참조를 정규화도 대 한 멤버를 연결 합니다. 자세한 내용은 <xref:System.Windows.DependencyProperty> 하 고 [XAML 개요 (WPF)](../wpf/advanced/xaml-overview-wpf.md)합니다.  
  
 DottedXamlName 다음 문법을 준수 해야 하는 형식의 값을 문자열:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>설명  
 완전 한 사양에 대해서 [ \[MS XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)합니다.
