---
description: '자세히 알아보기: ICLRHostBindingPolicyManager 인터페이스'
title: ICLRHostBindingPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 07a18d622ff8d8483fe6dcb0242cb5f1ee284b14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789946"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="2b068-103">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b068-103">ICLRHostBindingPolicyManager Interface</span></span>

<span data-ttu-id="2b068-104">호스트에서 현재 바인딩 정책을 평가 하 고 지정 된 어셈블리에 대 한 정책 변경 내용을 전달 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b068-104">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b068-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2b068-105">Methods</span></span>  
  
|<span data-ttu-id="2b068-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2b068-106">Method</span></span>|<span data-ttu-id="2b068-107">설명</span><span class="sxs-lookup"><span data-stu-id="2b068-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b068-108">EvaluatePolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="2b068-108">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="2b068-109">호스트를 대신 하 여 바인딩 정책을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b068-109">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="2b068-110">ModifyApplicationPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="2b068-110">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="2b068-111">지정 된 어셈블리에 대 한 바인딩 정책을 수정 하 고 정책의 새 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b068-111">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b068-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b068-112">Requirements</span></span>  

 <span data-ttu-id="2b068-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b068-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b068-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2b068-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b068-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b068-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b068-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b068-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b068-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b068-117">See also</span></span>

- [<span data-ttu-id="2b068-118">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b068-118">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="2b068-119">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b068-119">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="2b068-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b068-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
