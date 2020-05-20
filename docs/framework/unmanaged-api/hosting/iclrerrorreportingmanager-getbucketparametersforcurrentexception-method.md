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
ms.openlocfilehash: 969d74933e908674225684a2e77d5c4804b86122
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615646"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="75b15-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="75b15-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="75b15-103">호출 스레드의 현재 예외에 대 한 Watson 버킷을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75b15-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="75b15-104">*버킷은* 동일한 코드 오류와 관련 된 오류 데이터의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="75b15-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="75b15-105">*Watson* 은 예외와 관련 된 데이터를 수집 및 분석 하기 위한 일련의 기술을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75b15-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b15-106">구문</span><span class="sxs-lookup"><span data-stu-id="75b15-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75b15-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75b15-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="75b15-108">제한이 예외에 대 한 오류 데이터를 포함 하는 [BucketParameters](bucketparameters-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="75b15-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75b15-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75b15-109">Requirements</span></span>  
 <span data-ttu-id="75b15-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75b15-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75b15-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="75b15-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75b15-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75b15-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75b15-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75b15-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b15-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75b15-114">See also</span></span>

- [<span data-ttu-id="75b15-115">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75b15-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
