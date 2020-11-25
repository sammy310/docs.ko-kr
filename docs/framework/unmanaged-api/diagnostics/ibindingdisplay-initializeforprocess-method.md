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
ms.openlocfilehash: f9e65b49c9a3b506cba3493d81a40f2759dca781
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725151"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="4822e-102">IBindingDisplay::InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="4822e-102">IBindingDisplay::InitializeForProcess Method</span></span>

<span data-ttu-id="4822e-103">[IBindingDisplay](ibindingdisplay-interface.md) 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4822e-103">Initializes the [IBindingDisplay](ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4822e-104">구문</span><span class="sxs-lookup"><span data-stu-id="4822e-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4822e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4822e-105">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="4822e-106">진행 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4822e-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4822e-107">설명</span><span class="sxs-lookup"><span data-stu-id="4822e-107">Remarks</span></span>  

 <span data-ttu-id="4822e-108">디버거는 `InitializeForProcess` 만들 때 메서드를 호출 하 여 바인딩 디스플레이를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4822e-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="4822e-109">`InitializeForProcess` 생성 시에는의 다른 메서드가 호출 되기 전에를 호출 해야 합니다 `IBindingDisplay` .</span><span class="sxs-lookup"><span data-stu-id="4822e-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4822e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4822e-110">Requirements</span></span>  

 <span data-ttu-id="4822e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4822e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4822e-112">**헤더:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="4822e-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="4822e-113">**라이브러리:** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="4822e-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="4822e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4822e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4822e-115">참조</span><span class="sxs-lookup"><span data-stu-id="4822e-115">See also</span></span>

- [<span data-ttu-id="4822e-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4822e-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
