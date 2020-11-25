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
ms.openlocfilehash: d52f089923d16f93345444c07ff8e0619644f2eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725159"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="c1ba5-102">IBindingDisplay::GetCurrentDisplay 메서드</span><span class="sxs-lookup"><span data-stu-id="c1ba5-102">IBindingDisplay::GetCurrentDisplay Method</span></span>

<span data-ttu-id="c1ba5-103">현재 바인딩 표시 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ba5-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ba5-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1ba5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ba5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1ba5-105">Parameters</span></span>  

 `display`  
 <span data-ttu-id="c1ba5-106">[out, retval] 바인딩 표시 정보를 포함 하는 safearray에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ba5-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1ba5-107">설명</span><span class="sxs-lookup"><span data-stu-id="c1ba5-107">Remarks</span></span>  

 <span data-ttu-id="c1ba5-108">[IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) 메서드는 이전에 성공 했 고 프로그램은 디버거에서 중지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ba5-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="c1ba5-109">호출자는 `SAFEARRAY` [Safearraydestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)를 사용 하 여 반환 된 메모리의 할당을 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ba5-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ba5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1ba5-110">Requirements</span></span>  

 <span data-ttu-id="c1ba5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1ba5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ba5-112">**헤더:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="c1ba5-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="c1ba5-113">**라이브러리:** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="c1ba5-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="c1ba5-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ba5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ba5-115">참조</span><span class="sxs-lookup"><span data-stu-id="c1ba5-115">See also</span></span>

- [<span data-ttu-id="c1ba5-116">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1ba5-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="c1ba5-117">InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="c1ba5-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
