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
ms.openlocfilehash: aa1e85751f90c34d40e88207af5c7eed2dd1bb82
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197880"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="fc689-102">IBindingDisplay::InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="fc689-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="fc689-103">초기화 된 [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fc689-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc689-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc689-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc689-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc689-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="fc689-106">[in] 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="fc689-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc689-107">설명</span><span class="sxs-lookup"><span data-stu-id="fc689-107">Remarks</span></span>  
 <span data-ttu-id="fc689-108">디버거 호출을 `InitializeForProcess` 바인딩 표시 초기화를 만들 때 메서드.</span><span class="sxs-lookup"><span data-stu-id="fc689-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> `InitializeForProcess` <span data-ttu-id="fc689-109">다른 메서드 전에 호출 해야 `IBindingDisplay` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc689-109">must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc689-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc689-110">Requirements</span></span>  
 <span data-ttu-id="fc689-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc689-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc689-112">**헤더:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="fc689-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="fc689-113">**라이브러리:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="fc689-113">**Library:** BindingDisplay.idl</span></span>  
  
 **<span data-ttu-id="fc689-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="fc689-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc689-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc689-115">See also</span></span>

- [<span data-ttu-id="fc689-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc689-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
