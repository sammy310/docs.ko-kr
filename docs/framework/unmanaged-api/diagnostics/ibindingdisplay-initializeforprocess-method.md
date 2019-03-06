---
title: IBindingDisplay::InitializeForProcess 메서드
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aabad159b521207fed976636ae8b9e338f09ac42
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466182"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="98f4b-102">IBindingDisplay::InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="98f4b-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="98f4b-103">초기화 된 [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="98f4b-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f4b-104">구문</span><span class="sxs-lookup"><span data-stu-id="98f4b-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98f4b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98f4b-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="98f4b-106">[in] 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="98f4b-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98f4b-107">설명</span><span class="sxs-lookup"><span data-stu-id="98f4b-107">Remarks</span></span>  
 <span data-ttu-id="98f4b-108">디버거 호출을 `InitializeForProcess` 바인딩 표시 초기화를 만들 때 메서드.</span><span class="sxs-lookup"><span data-stu-id="98f4b-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="98f4b-109">`InitializeForProcess` 다른 메서드 전에 호출 해야 `IBindingDisplay` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="98f4b-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98f4b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98f4b-110">Requirements</span></span>  
 <span data-ttu-id="98f4b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98f4b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98f4b-112">**헤더:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="98f4b-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="98f4b-113">**라이브러리:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="98f4b-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="98f4b-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98f4b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f4b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="98f4b-115">See also</span></span>
- [<span data-ttu-id="98f4b-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98f4b-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
