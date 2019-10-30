---
title: InheritsFrom 함수 (관리 되지 않는 API 참조)
description: InheritsFrom 함수는 클래스 또는 인스턴스가 특정 부모 클래스에서 파생 되는지 여부를 확인 합니다.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6bda63377251e3a208dfb1620896535ccdf8ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127427"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="69c0d-103">InheritsFrom 함수</span><span class="sxs-lookup"><span data-stu-id="69c0d-103">InheritsFrom function</span></span>
<span data-ttu-id="69c0d-104">현재 클래스 또는 인스턴스가 지정된 부모 클래스에서 파생되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="69c0d-105">구문</span><span class="sxs-lookup"><span data-stu-id="69c0d-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="69c0d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69c0d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="69c0d-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="69c0d-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="69c0d-109">진행 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-109">[in] The name of the class.</span></span> <span data-ttu-id="69c0d-110">`wszAncestor`는 유효한 `LPCWSTR`을 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="69c0d-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="69c0d-111">Return value</span></span>

<span data-ttu-id="69c0d-112">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="69c0d-113">상수</span><span class="sxs-lookup"><span data-stu-id="69c0d-113">Constant</span></span>  |<span data-ttu-id="69c0d-114">값</span><span class="sxs-lookup"><span data-stu-id="69c0d-114">Value</span></span>  |<span data-ttu-id="69c0d-115">설명</span><span class="sxs-lookup"><span data-stu-id="69c0d-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="69c0d-116">0</span><span class="sxs-lookup"><span data-stu-id="69c0d-116">0</span></span> | <span data-ttu-id="69c0d-117">현재 개체는 `wszAncestor`에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="69c0d-118">1</span><span class="sxs-lookup"><span data-stu-id="69c0d-118">1</span></span> | <span data-ttu-id="69c0d-119">현재 개체가 `wszAncestor`에서 상속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="69c0d-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="69c0d-120">0x80041008</span></span> | <span data-ttu-id="69c0d-121">`wszAncestor`가 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="69c0d-122">주의</span><span class="sxs-lookup"><span data-stu-id="69c0d-122">Remarks</span></span>

<span data-ttu-id="69c0d-123">이 함수는 [IWbemClassObject:: InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="69c0d-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="69c0d-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69c0d-124">Requirements</span></span>  
 <span data-ttu-id="69c0d-125">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69c0d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69c0d-126">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="69c0d-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="69c0d-127">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="69c0d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c0d-128">참조</span><span class="sxs-lookup"><span data-stu-id="69c0d-128">See also</span></span>

- [<span data-ttu-id="69c0d-129">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="69c0d-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
