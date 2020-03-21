---
title: 스폰인스턴스 함수(관리되지 않는 API 참조)
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
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176723"
---
# <a name="spawninstance-function"></a><span data-ttu-id="6511e-103">SpawnInstance 함수</span><span class="sxs-lookup"><span data-stu-id="6511e-103">SpawnInstance function</span></span>
<span data-ttu-id="6511e-104">클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-104">Creates a new instance of a class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6511e-105">구문</span><span class="sxs-lookup"><span data-stu-id="6511e-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a><span data-ttu-id="6511e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6511e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6511e-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6511e-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="6511e-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-109">[in] Reserved.</span></span> <span data-ttu-id="6511e-110">이 매개변수는 0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="6511e-111">【아웃】 클래스의 새 인스턴스에 대한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="6511e-112">오류가 발생하면 새 개체가 반환되지 않고 `ppNewInstance` 수정되지 않은 상태로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="6511e-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="6511e-113">Return value</span></span>

<span data-ttu-id="6511e-114">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6511e-115">지속적임</span><span class="sxs-lookup"><span data-stu-id="6511e-115">Constant</span></span>  |<span data-ttu-id="6511e-116">값</span><span class="sxs-lookup"><span data-stu-id="6511e-116">Value</span></span>  |<span data-ttu-id="6511e-117">Description</span><span class="sxs-lookup"><span data-stu-id="6511e-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="6511e-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="6511e-118">0x80041020</span></span> | <span data-ttu-id="6511e-119">`ptr`유효한 클래스 정의이며 새 인스턴스를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="6511e-120">불완전하거나 [PutClassWmi를](putclasswmi.md)호출하여 Windows 관리에 등록되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6511e-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6511e-121">0x80041006</span></span> | <span data-ttu-id="6511e-122">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6511e-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6511e-123">0x80041008</span></span> | <span data-ttu-id="6511e-124">`ppNewClass`은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6511e-125">0</span><span class="sxs-lookup"><span data-stu-id="6511e-125">0</span></span> | <span data-ttu-id="6511e-126">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6511e-127">설명</span><span class="sxs-lookup"><span data-stu-id="6511e-127">Remarks</span></span>

<span data-ttu-id="6511e-128">이 함수는 [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="6511e-129">`ptr`Windows 관리에서 가져온 클래스 정의여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="6511e-130">인스턴스에서 인스턴스를 스폰하는 것은 지원되지만 반환된 인스턴스는 비어 있습니다.) 그런 다음 이 클래스 정의를 사용하여 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="6511e-131">Windows 관리에 인스턴스를 작성하려면 [PutInstanceWmi](putinstancewmi.md) 함수를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="6511e-132">자동으로 반환되는 `ppNewClass` 새 개체는 현재 개체의 하위 클래스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="6511e-133">이 동작은 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="6511e-134">하위 클래스(파생 클래스)를 만들 수 있는 다른 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6511e-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="6511e-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6511e-135">Requirements</span></span>  
 <span data-ttu-id="6511e-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6511e-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6511e-137">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6511e-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6511e-138">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6511e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6511e-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6511e-139">See also</span></span>

- [<span data-ttu-id="6511e-140">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="6511e-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
