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
ms.openlocfilehash: c19b49e9e9d4e388706a96ff54d588d5aeff99b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775954"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="8178d-102">IBindingDisplay::InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="8178d-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="8178d-103">초기화 된 [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8178d-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8178d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8178d-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8178d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8178d-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="8178d-106">[in] 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8178d-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8178d-107">설명</span><span class="sxs-lookup"><span data-stu-id="8178d-107">Remarks</span></span>  
 <span data-ttu-id="8178d-108">디버거 호출을 `InitializeForProcess` 바인딩 표시 초기화를 만들 때 메서드.</span><span class="sxs-lookup"><span data-stu-id="8178d-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="8178d-109">`InitializeForProcess` 다른 메서드 전에 호출 해야 `IBindingDisplay` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8178d-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8178d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8178d-110">Requirements</span></span>  
 <span data-ttu-id="8178d-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8178d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8178d-112">**헤더:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="8178d-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="8178d-113">**라이브러리:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="8178d-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="8178d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8178d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8178d-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="8178d-115">See also</span></span>

- [<span data-ttu-id="8178d-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8178d-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
