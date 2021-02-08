---
description: '자세히 알아보기: IBindingDisplay:: GetCurrentDisplay 메서드'
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
ms.openlocfilehash: 680a91c8025ac3247701c14c23f442da5e304ecb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800424"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="d14f4-103">IBindingDisplay::GetCurrentDisplay 메서드</span><span class="sxs-lookup"><span data-stu-id="d14f4-103">IBindingDisplay::GetCurrentDisplay Method</span></span>

<span data-ttu-id="d14f4-104">현재 바인딩 표시 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14f4-104">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d14f4-105">구문</span><span class="sxs-lookup"><span data-stu-id="d14f4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d14f4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d14f4-106">Parameters</span></span>  

 `display`  
 <span data-ttu-id="d14f4-107">[out, retval] 바인딩 표시 정보를 포함 하는 safearray에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d14f4-107">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d14f4-108">설명</span><span class="sxs-lookup"><span data-stu-id="d14f4-108">Remarks</span></span>  

 <span data-ttu-id="d14f4-109">[IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) 메서드는 이전에 성공 했 고 프로그램은 디버거에서 중지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14f4-109">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="d14f4-110">호출자는 `SAFEARRAY` [Safearraydestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)를 사용 하 여 반환 된 메모리의 할당을 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14f4-110">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d14f4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d14f4-111">Requirements</span></span>  

 <span data-ttu-id="d14f4-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d14f4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d14f4-113">**헤더:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="d14f4-113">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="d14f4-114">**라이브러리:** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="d14f4-114">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="d14f4-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d14f4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14f4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d14f4-116">See also</span></span>

- [<span data-ttu-id="d14f4-117">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d14f4-117">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="d14f4-118">InitializeForProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="d14f4-118">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
