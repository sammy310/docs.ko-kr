---
title: ClaimSet에서 클레임 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: 42e6ee682220913f872da337eb41f6c290082988
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137126"
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="cbd5c-102">ClaimSet에서 클레임 찾기</span><span class="sxs-lookup"><span data-stu-id="cbd5c-102">Finding Claims in a ClaimSet</span></span>
<span data-ttu-id="cbd5c-103">클레임 기준 권한 부여를 사용하는 경우 <xref:System.IdentityModel.Claims.ClaimSet>의 콘텐츠에서 특정 형식의 클레임을 확인하는 작업이 일반적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbd5c-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="cbd5c-104"><xref:System.IdentityModel.Claims.ClaimSet>에 특정 클레임이 있는지 확인하려면 <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd5c-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="cbd5c-105">이 메서드가 <xref:System.IdentityModel.Claims.ClaimSet>을 직접 반복하는 것보다 더 성능이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd5c-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="cbd5c-106">다음은 이렇게 사용하는 경우의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cbd5c-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="cbd5c-107">`claimType` 및 `claimRight` 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd5c-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="cbd5c-108">이 경우 매개 변수에서는 모든 클레임 형식과 클레임 권한을 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="cbd5c-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbd5c-109">예제</span><span class="sxs-lookup"><span data-stu-id="cbd5c-109">Example</span></span>  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cbd5c-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="cbd5c-110">See also</span></span>

- [<span data-ttu-id="cbd5c-111">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="cbd5c-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
