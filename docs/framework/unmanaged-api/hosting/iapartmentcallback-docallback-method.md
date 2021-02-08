---
description: IApartmentCallback::D oCallback 메서드에 대해 자세히 알아보세요.
title: IApartmentCallback::DoCallback 메서드
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
ms.openlocfilehash: 65b7f496f953f08e099bf13ef8212c7d6e1026ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785108"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="da52c-103">IApartmentCallback::DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="da52c-103">IApartmentCallback::DoCallback Method</span></span>

<span data-ttu-id="da52c-104">아파트 내에서 지정 된 함수를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da52c-104">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da52c-105">구문</span><span class="sxs-lookup"><span data-stu-id="da52c-105">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da52c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da52c-106">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="da52c-107">진행 아파트 내에서 실행 되는 함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da52c-107">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="da52c-108">진행 함수 인수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da52c-108">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da52c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da52c-109">Requirements</span></span>  

 <span data-ttu-id="da52c-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da52c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da52c-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="da52c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da52c-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da52c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da52c-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da52c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da52c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da52c-114">See also</span></span>

- [<span data-ttu-id="da52c-115">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da52c-115">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
