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
# <a name="systemconvert-methods"></a><span data-ttu-id="578bf-102">System.Convert 메서드</span><span class="sxs-lookup"><span data-stu-id="578bf-102">System.Convert Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="578bf-103">다음을 지원 하지 않습니다 <xref:System.Convert> 메서드.</span><span class="sxs-lookup"><span data-stu-id="578bf-103">does not support the following <xref:System.Convert> methods.</span></span>  
  
-   <span data-ttu-id="578bf-104"><xref:System.IFormatProvider> 매개 변수를 사용하는 버전</span><span class="sxs-lookup"><span data-stu-id="578bf-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>  
  
-   <span data-ttu-id="578bf-105">문자 배열 또는 바이트 배열과 관련된 메서드</span><span class="sxs-lookup"><span data-stu-id="578bf-105">Methods that involve char arrays or byte arrays:</span></span>  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   <span data-ttu-id="578bf-106">다음과 같은 메서드</span><span class="sxs-lookup"><span data-stu-id="578bf-106">The following methods:</span></span>  
  
    -   `public static <Type2> To<Type2>(<Type1> value);` <span data-ttu-id="578bf-107">형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="578bf-107">where</span></span>  
  
         `Type1` <span data-ttu-id="578bf-108">및 `Type2` 는 각각 `sbyte`를 `uint`를 `ulong`, 또는 `ushort`합니다.</span><span class="sxs-lookup"><span data-stu-id="578bf-108">and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>  
  
    -   <span data-ttu-id="578bf-109">C#: </span><span class="sxs-lookup"><span data-stu-id="578bf-109">C#:</span></span>  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   <span data-ttu-id="578bf-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="578bf-110">Visual Basic:</span></span>  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a><span data-ttu-id="578bf-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="578bf-111">See also</span></span>

- [<span data-ttu-id="578bf-112">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="578bf-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
