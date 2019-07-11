---
title: SpawnInstance 함수 (관리 되지 않는 API 참조)
description: SpawnInstance 함수는 클래스의 새 인스턴스를 만듭니다.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97a3ab62cda82526a7ad8b8e5d985d9fce7d6f07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783078"
---
# <a name="spawninstance-function"></a><span data-ttu-id="57dc7-103">SpawnInstance 함수</span><span class="sxs-lookup"><span data-stu-id="57dc7-103">SpawnInstance function</span></span>
<span data-ttu-id="57dc7-104">클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="57dc7-105">구문</span><span class="sxs-lookup"><span data-stu-id="57dc7-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="57dc7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57dc7-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="57dc7-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="57dc7-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="57dc7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="57dc7-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-109">[in] Reserved.</span></span> <span data-ttu-id="57dc7-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="57dc7-111">[out] 클래스의 새 인스턴스에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="57dc7-112">오류가 발생 하는 새 개체가 없는 경우 반환 및 `ppNewInstance` 왼쪽 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="57dc7-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="57dc7-113">Return value</span></span>

<span data-ttu-id="57dc7-114">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="57dc7-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="57dc7-115">상수</span><span class="sxs-lookup"><span data-stu-id="57dc7-115">Constant</span></span>  |<span data-ttu-id="57dc7-116">값</span><span class="sxs-lookup"><span data-stu-id="57dc7-116">Value</span></span>  |<span data-ttu-id="57dc7-117">설명</span><span class="sxs-lookup"><span data-stu-id="57dc7-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="57dc7-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="57dc7-118">0x80041020</span></span> | <span data-ttu-id="57dc7-119">`ptr` 올바른 클래스 정의가 아닌 경우 및 새 인스턴스를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="57dc7-120">완료 되지 않은 또는 등록 되지 않은 Windows 관리를 사용 하 여 호출 하 여 [PutClassWmi](putclasswmi.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="57dc7-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="57dc7-121">0x80041006</span></span> | <span data-ttu-id="57dc7-122">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="57dc7-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="57dc7-123">0x80041008</span></span> | <span data-ttu-id="57dc7-124">`ppNewClass`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="57dc7-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="57dc7-125">0</span><span class="sxs-lookup"><span data-stu-id="57dc7-125">0</span></span> | <span data-ttu-id="57dc7-126">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="57dc7-127">설명</span><span class="sxs-lookup"><span data-stu-id="57dc7-127">Remarks</span></span>

<span data-ttu-id="57dc7-128">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) 메서드.</span><span class="sxs-lookup"><span data-stu-id="57dc7-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="57dc7-129">`ptr` 클래스 정의에서 받아야 Windows 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="57dc7-130">(인스턴스에서 인스턴스 생성은 지원 하지만 반환 된 인스턴스에만 비어 있습니다.) 그런 다음이 클래스 정의 사용 하 여 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="57dc7-131">에 대 한 호출을 [PutInstanceWmi](putinstancewmi.md) 함수는 Windows 관리 인스턴스를 작성 하려는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="57dc7-132">반환 되는 새 개체 `ppNewClass` 현재 개체의 하위 클래스는 자동으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="57dc7-133">이 동작을 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="57dc7-134">서브 클래스 (파생된 클래스)을 만들 수 있는 다른 메서드가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="57dc7-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="57dc7-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57dc7-135">Requirements</span></span>  
 <span data-ttu-id="57dc7-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="57dc7-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57dc7-137">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="57dc7-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="57dc7-138">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="57dc7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57dc7-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="57dc7-139">See also</span></span>

- [<span data-ttu-id="57dc7-140">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="57dc7-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
