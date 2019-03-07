---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3877f00a22c43ef5f22974b621b32b78ce15d795
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494469"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="51ade-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="51ade-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="51ade-103">Watson 버킷이 호출 스레드에서 현재 예외를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="51ade-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="51ade-104">A *버킷* 는 동일한 코드 오류에 관련 된 오류 데이터의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="51ade-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="51ade-105">*Watson* 예외와 연결 된 데이터 수집 및 분석에 대 한 기술 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51ade-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ade-106">구문</span><span class="sxs-lookup"><span data-stu-id="51ade-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51ade-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51ade-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="51ade-108">[out] 에 대 한 포인터를 [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) 예외에 대 한 오류 데이터를 포함 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="51ade-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ade-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51ade-109">Requirements</span></span>  
 <span data-ttu-id="51ade-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="51ade-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ade-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51ade-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51ade-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="51ade-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51ade-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ade-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ade-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="51ade-114">See also</span></span>
- [<span data-ttu-id="51ade-115">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51ade-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
