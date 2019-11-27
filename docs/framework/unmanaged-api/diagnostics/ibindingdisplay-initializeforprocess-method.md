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
ms.openlocfilehash: bb796a12868cc3e44394ab493f7838dc48ab4dc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448489"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="96af1-102">IBindingDisplay::InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="96af1-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="96af1-103">[IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="96af1-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96af1-104">구문</span><span class="sxs-lookup"><span data-stu-id="96af1-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96af1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96af1-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="96af1-106">진행 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="96af1-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96af1-107">주의</span><span class="sxs-lookup"><span data-stu-id="96af1-107">Remarks</span></span>  
 <span data-ttu-id="96af1-108">디버거는 만든 시간에 `InitializeForProcess` 메서드를 호출 하 여 바인딩 표시를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="96af1-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="96af1-109">`InitializeForProcess` `IBindingDisplay`에서 다른 메서드를 호출 하기 전에 생성 시 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96af1-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96af1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96af1-110">Requirements</span></span>  
 <span data-ttu-id="96af1-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96af1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96af1-112">**헤더:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="96af1-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="96af1-113">**라이브러리:** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="96af1-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="96af1-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96af1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96af1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96af1-115">See also</span></span>

- [<span data-ttu-id="96af1-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96af1-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
