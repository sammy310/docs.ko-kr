---
title: IBindingDisplay::GetCurrentDisplay 메서드
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: 9294dbf1caddd4b607185de54efd2b4764e6ca35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448499"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="118bf-102">IBindingDisplay::GetCurrentDisplay 메서드</span><span class="sxs-lookup"><span data-stu-id="118bf-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="118bf-103">현재 바인딩 표시 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="118bf-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="118bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="118bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="118bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="118bf-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="118bf-106">[out, retval] 바인딩 표시 정보를 포함 하는 safearray에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="118bf-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="118bf-107">주의</span><span class="sxs-lookup"><span data-stu-id="118bf-107">Remarks</span></span>  
 <span data-ttu-id="118bf-108">[IBindingDisplay:: InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) 메서드는 이전에 성공 했 고 프로그램은 디버거에서 중지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="118bf-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="118bf-109">호출자는 [Safearraydestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)를 사용 하 여 반환 된 `SAFEARRAY` 메모리의 할당을 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="118bf-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="118bf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="118bf-110">Requirements</span></span>  
 <span data-ttu-id="118bf-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="118bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="118bf-112">**헤더:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="118bf-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="118bf-113">**라이브러리:** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="118bf-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="118bf-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="118bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118bf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="118bf-115">See also</span></span>

- [<span data-ttu-id="118bf-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="118bf-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="118bf-117">InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="118bf-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
