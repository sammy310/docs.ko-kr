---
title: CoInitializeEE 함수
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 57508a2df3a49c39d25347f2a3038442c37278da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616764"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="c9056-102">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="c9056-102">CoInitializeEE Function</span></span>
<span data-ttu-id="c9056-103">공용 언어 런타임 실행 엔진이 프로세스로 로드 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="c9056-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="c9056-105">대신 [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9056-106">구문</span><span class="sxs-lookup"><span data-stu-id="c9056-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9056-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c9056-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="c9056-108">진행 [COINITIEE](../metadata/coinitiee-enumeration.md) 열거형 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9056-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="c9056-109">Return Value</span></span>  
 <span data-ttu-id="c9056-110">이 메서드는 Winerror.h에 정의 된 표준 COM 오류 코드와 다음 표에 있는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="c9056-111">반환 코드</span><span class="sxs-lookup"><span data-stu-id="c9056-111">Return code</span></span>|<span data-ttu-id="c9056-112">설명</span><span class="sxs-lookup"><span data-stu-id="c9056-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c9056-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9056-113">S_OK</span></span>|<span data-ttu-id="c9056-114">실행 엔진이 로드 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="c9056-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c9056-115">S_FALSE</span></span>|<span data-ttu-id="c9056-116">실행 엔진이 이미 로드 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="c9056-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9056-117">E_FAIL</span></span>|<span data-ttu-id="c9056-118">실행 엔진을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9056-119">설명</span><span class="sxs-lookup"><span data-stu-id="c9056-119">Remarks</span></span>  
 <span data-ttu-id="c9056-120">이 메서드는 이전에 로드 되지 않은 경우 실행 엔진을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9056-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9056-121">Requirements</span></span>  
 <span data-ttu-id="c9056-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9056-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9056-123">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c9056-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9056-124">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9056-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c9056-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9056-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9056-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9056-126">See also</span></span>

- [<span data-ttu-id="c9056-127">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="c9056-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
