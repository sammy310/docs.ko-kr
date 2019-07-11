---
title: BeginMethodEnumeration 함수 (관리 되지 않는 API 참조)
description: BeginMethodEnumeration 함수 개체의 메서드는 열거를 시작합니다.
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46ef53acdfa06b0c2be9d2aa55e89ce8fa34dfb0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761745"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="3edf9-103">BeginEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="3edf9-103">BeginEnumeration function</span></span>
<span data-ttu-id="3edf9-104">개체에 대해 사용할 수 있는 방법의 열거형을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="3edf9-105">구문</span><span class="sxs-lookup"><span data-stu-id="3edf9-105">Syntax</span></span>  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="3edf9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3edf9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3edf9-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3edf9-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3edf9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="3edf9-109">[in] 영 (0) 모든 메서드 또는 열거형의 범위를 지정 하는 플래그에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="3edf9-110">에 정의 된 다음 플래그를 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="3edf9-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="3edf9-111">상수</span><span class="sxs-lookup"><span data-stu-id="3edf9-111">Constant</span></span>  |<span data-ttu-id="3edf9-112">값</span><span class="sxs-lookup"><span data-stu-id="3edf9-112">Value</span></span>  |<span data-ttu-id="3edf9-113">설명</span><span class="sxs-lookup"><span data-stu-id="3edf9-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="3edf9-114">0x10</span><span class="sxs-lookup"><span data-stu-id="3edf9-114">0x10</span></span> | <span data-ttu-id="3edf9-115">열거형 클래스 자체에 정의 된 메서드를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="3edf9-116">0x20</span><span class="sxs-lookup"><span data-stu-id="3edf9-116">0x20</span></span> | <span data-ttu-id="3edf9-117">열거형 기본 클래스에서 상속 된 속성을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="3edf9-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="3edf9-118">Return value</span></span>

<span data-ttu-id="3edf9-119">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="3edf9-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3edf9-120">상수</span><span class="sxs-lookup"><span data-stu-id="3edf9-120">Constant</span></span>  |<span data-ttu-id="3edf9-121">값</span><span class="sxs-lookup"><span data-stu-id="3edf9-121">Value</span></span>  |<span data-ttu-id="3edf9-122">Description</span><span class="sxs-lookup"><span data-stu-id="3edf9-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3edf9-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3edf9-123">0x80041008</span></span> | <span data-ttu-id="3edf9-124">`lEnnumFlags` 0이 아닌 값 이며 지정된 된 플래그 중 하나가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3edf9-125">0</span><span class="sxs-lookup"><span data-stu-id="3edf9-125">0</span></span> | <span data-ttu-id="3edf9-126">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3edf9-127">설명</span><span class="sxs-lookup"><span data-stu-id="3edf9-127">Remarks</span></span>

<span data-ttu-id="3edf9-128">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3edf9-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="3edf9-129">이 메서드 호출은 현재 개체가 클래스 정의 하는 경우에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="3edf9-130">조작 메서드를 사용할 수 없기 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="3edf9-131">지정된 된 인스턴스에 대 한 변형 되지 메서드를 열거 순서는 보장 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)합니다.</span><span class="sxs-lookup"><span data-stu-id="3edf9-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="3edf9-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3edf9-132">Requirements</span></span>  
 <span data-ttu-id="3edf9-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3edf9-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3edf9-134">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3edf9-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3edf9-135">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3edf9-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3edf9-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="3edf9-136">See also</span></span>

- [<span data-ttu-id="3edf9-137">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3edf9-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
