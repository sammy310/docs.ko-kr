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
ms.openlocfilehash: 6fe8c3266a8c9a52cd1022589cd68485c4326fd1
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442191"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="e1d78-102">IBindingDisplay::GetCurrentDisplay 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d78-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="e1d78-103">현재 바인딩 표시 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d78-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1d78-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1d78-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1d78-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1d78-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="e1d78-106">[out, retval] 바인딩 표시 정보를 포함 하는 safearray에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1d78-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1d78-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1d78-107">Remarks</span></span>  
 <span data-ttu-id="e1d78-108">[IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) 메서드는 이전에 성공 했 고 프로그램은 디버거에서 중지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d78-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="e1d78-109">호출자는 `SAFEARRAY` [Safearraydestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)를 사용 하 여 반환 된 메모리의 할당을 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d78-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1d78-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1d78-110">Requirements</span></span>  
 <span data-ttu-id="e1d78-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1d78-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1d78-112">**헤더:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="e1d78-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="e1d78-113">**라이브러리:** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="e1d78-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="e1d78-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1d78-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d78-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1d78-115">See also</span></span>

- [<span data-ttu-id="e1d78-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1d78-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="e1d78-117">InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d78-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
