---
title: '방법: Point4D 구조체가 동일한지 여부 테스트'
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: ce1188e99ef2b0682427cc2e227aaccd27f7c4f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050638"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a><span data-ttu-id="fa640-102">방법: Point4D 구조체가 동일한지 여부 테스트</span><span class="sxs-lookup"><span data-stu-id="fa640-102">How to: Test Point4D structures for equality and inequality</span></span>
<span data-ttu-id="fa640-103">이 예제에서는 테스트 <xref:System.Windows.Media.Media3D.Point4D> 같음 및 다름에 대 한 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="fa640-103">This example shows how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality.</span></span>  
  
 <span data-ttu-id="fa640-104">다음 코드를 테스트 하는 방법을 보여 줍니다 <xref:System.Windows.Media.Media3D.Point4D> 같음 및 같지 않음 사용에 대 한 구조는 <xref:System.Windows.Media.Media3D.Point4D> 같음 메서드.</span><span class="sxs-lookup"><span data-stu-id="fa640-104">The following code illustrates how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality using the <xref:System.Windows.Media.Media3D.Point4D> equality methods.</span></span>  <span data-ttu-id="fa640-105"><xref:System.Windows.Media.Media3D.Point4D> 구조는 오버 로드 된 같음을 사용 하 여 같음 테스트 (`==`) 연산자를 오버 로드 된 같지 않음을 사용 하 여 다른 지에 대 한 다음 (`!=`) 연산자를 마지막으로 <xref:System.Windows.Media.Media3D.Point3D> 구조 및 <xref:System.Windows.Media.Media3D.Point4D> 구조 정적을 사용 하 여 같은지 확인 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fa640-105">The <xref:System.Windows.Media.Media3D.Point4D> structures are tested for equality using the overloaded equality (`==`) operator, then for inequality using the overloaded inequality (`!=`) operator, and finally a <xref:System.Windows.Media.Media3D.Point3D> structure and a <xref:System.Windows.Media.Media3D.Point4D> structure are checked for equality using the static <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa640-106">예제</span><span class="sxs-lookup"><span data-stu-id="fa640-106">Example</span></span>  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a><span data-ttu-id="fa640-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa640-107">See also</span></span>

- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
