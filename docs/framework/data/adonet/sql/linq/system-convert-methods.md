---
title: System.Convert 메서드
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: 0d98d159c24e1a47723aeb07a9654fe22b1d9464
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198220"
---
# <a name="systemconvert-methods"></a>System.Convert 메서드
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 다음을 지원 하지 않습니다 <xref:System.Convert> 메서드.  
  
-   <xref:System.IFormatProvider> 매개 변수를 사용하는 버전  
  
-   문자 배열 또는 바이트 배열과 관련된 메서드  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   다음과 같은 메서드  
  
    -   `public static <Type2> To<Type2>(<Type1> value);` 형식에 대한 설명  
  
         `Type1` 및 `Type2` 는 각각 `sbyte`를 `uint`를 `ulong`, 또는 `ushort`합니다.  
  
    -   C#:   
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   Visual Basic:  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a>참고자료

- [데이터 형식 및 함수](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
