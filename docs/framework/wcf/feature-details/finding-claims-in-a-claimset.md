---
description: '자세한 정보: ClaimSet에서 클레임 찾기'
title: ClaimSet에서 클레임 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: 3ac4553e50f98f54e0a23aa9d759d7ae2f7caa8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802933"
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="09b0e-103">ClaimSet에서 클레임 찾기</span><span class="sxs-lookup"><span data-stu-id="09b0e-103">Finding Claims in a ClaimSet</span></span>

<span data-ttu-id="09b0e-104"><xref:System.IdentityModel.Claims.ClaimSet>클레임 기반 권한 부여를 사용 하는 경우 특정 유형의 클레임에 대 한의 콘텐츠를 검사 하는 것은 일반적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="09b0e-104">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="09b0e-105"><xref:System.IdentityModel.Claims.ClaimSet>특정 클레임이 있는지 확인 하려면 메서드를 사용 합니다 <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> .</span><span class="sxs-lookup"><span data-stu-id="09b0e-105">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="09b0e-106">이 메서드가 <xref:System.IdentityModel.Claims.ClaimSet>을 직접 반복하는 것보다 더 성능이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09b0e-106">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="09b0e-107">다음은 이렇게 사용하는 경우의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="09b0e-107">The following example demonstrates this usage.</span></span> <span data-ttu-id="09b0e-108">`claimType` 및 `claimRight` 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09b0e-108">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="09b0e-109">이 경우 매개 변수에서는 모든 클레임 형식과 클레임 권한을 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="09b0e-109">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09b0e-110">예제</span><span class="sxs-lookup"><span data-stu-id="09b0e-110">Example</span></span>  

 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="09b0e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09b0e-111">See also</span></span>

- [<span data-ttu-id="09b0e-112">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="09b0e-112">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
