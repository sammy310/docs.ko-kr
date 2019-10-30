---
title: BeginMethodEnumeration 함수 (관리 되지 않는 API 참조)
description: BeginMethodEnumeration 함수는 개체의 메서드 열거를 시작 합니다.
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
ms.openlocfilehash: a27787052757098d4edb2d8516e22d8a03b7009a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138796"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="1f46b-103">BeginEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="1f46b-103">BeginEnumeration function</span></span>
<span data-ttu-id="1f46b-104">개체에 사용할 수 있는 메서드의 열거를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="1f46b-105">구문</span><span class="sxs-lookup"><span data-stu-id="1f46b-105">Syntax</span></span>  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="1f46b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f46b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1f46b-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1f46b-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="1f46b-109">진행 모든 메서드의 경우 0이 고, 열거형의 범위를 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="1f46b-110">다음 플래그는 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="1f46b-111">상수</span><span class="sxs-lookup"><span data-stu-id="1f46b-111">Constant</span></span>  |<span data-ttu-id="1f46b-112">값</span><span class="sxs-lookup"><span data-stu-id="1f46b-112">Value</span></span>  |<span data-ttu-id="1f46b-113">설명</span><span class="sxs-lookup"><span data-stu-id="1f46b-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="1f46b-114">0x10</span><span class="sxs-lookup"><span data-stu-id="1f46b-114">0x10</span></span> | <span data-ttu-id="1f46b-115">클래스 자체에 정의 된 메서드로 열거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="1f46b-116">0x20</span><span class="sxs-lookup"><span data-stu-id="1f46b-116">0x20</span></span> | <span data-ttu-id="1f46b-117">기본 클래스에서 상속 되는 속성으로 열거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="1f46b-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f46b-118">Return value</span></span>

<span data-ttu-id="1f46b-119">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1f46b-120">상수</span><span class="sxs-lookup"><span data-stu-id="1f46b-120">Constant</span></span>  |<span data-ttu-id="1f46b-121">값</span><span class="sxs-lookup"><span data-stu-id="1f46b-121">Value</span></span>  |<span data-ttu-id="1f46b-122">설명</span><span class="sxs-lookup"><span data-stu-id="1f46b-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1f46b-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1f46b-123">0x80041008</span></span> | <span data-ttu-id="1f46b-124">`lEnnumFlags` 0이 아니고 지정 된 플래그 중 하나가 아닌 경우</span><span class="sxs-lookup"><span data-stu-id="1f46b-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1f46b-125">0</span><span class="sxs-lookup"><span data-stu-id="1f46b-125">0</span></span> | <span data-ttu-id="1f46b-126">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1f46b-127">주의</span><span class="sxs-lookup"><span data-stu-id="1f46b-127">Remarks</span></span>

<span data-ttu-id="1f46b-128">이 함수는 [IWbemClassObject:: BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="1f46b-129">이 메서드 호출은 현재 개체가 클래스 정의 인 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="1f46b-130">인스턴스를 가리키는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포인터에서 메서드 조작을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="1f46b-131">메서드가 열거 되는 순서는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)의 지정 된 인스턴스에 대해 고정이 되도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f46b-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="1f46b-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f46b-132">Requirements</span></span>  
 <span data-ttu-id="1f46b-133">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f46b-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f46b-134">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="1f46b-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1f46b-135">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1f46b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f46b-136">참조</span><span class="sxs-lookup"><span data-stu-id="1f46b-136">See also</span></span>

- [<span data-ttu-id="1f46b-137">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="1f46b-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
