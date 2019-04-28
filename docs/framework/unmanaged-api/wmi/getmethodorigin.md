---
title: GetMethodOrigin 함수 (관리 되지 않는 API 참조)
description: GetMethodOrigin 함수 메서드 선언 되는 클래스를 결정 합니다.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193caa894b8697a65e8821c01a63dde9cc5b5ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608946"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="e1406-103">GetMethodOrigin 함수</span><span class="sxs-lookup"><span data-stu-id="e1406-103">GetMethodOrigin function</span></span>
<span data-ttu-id="e1406-104">메서드가 선언되는 클래스를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e1406-105">구문</span><span class="sxs-lookup"><span data-stu-id="e1406-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="e1406-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1406-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e1406-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e1406-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e1406-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="e1406-109">[in] 소유 하는 클래스를 요청 하는 개체에 대 한 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="e1406-110">[out] 메서드를 소유 하는 클래스의 이름을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="e1406-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="e1406-111">Return value</span></span>

<span data-ttu-id="e1406-112">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="e1406-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e1406-113">상수</span><span class="sxs-lookup"><span data-stu-id="e1406-113">Constant</span></span>  |<span data-ttu-id="e1406-114">값</span><span class="sxs-lookup"><span data-stu-id="e1406-114">Value</span></span>  |<span data-ttu-id="e1406-115">설명</span><span class="sxs-lookup"><span data-stu-id="e1406-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e1406-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e1406-116">0x80041002</span></span> | <span data-ttu-id="e1406-117">지정된 된 메서드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e1406-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e1406-118">0x80041008</span></span> | <span data-ttu-id="e1406-119">하나 이상의 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e1406-120">0</span><span class="sxs-lookup"><span data-stu-id="e1406-120">0</span></span> | <span data-ttu-id="e1406-121">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e1406-122">설명</span><span class="sxs-lookup"><span data-stu-id="e1406-122">Remarks</span></span>

<span data-ttu-id="e1406-123">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e1406-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="e1406-124">클래스는 하나 이상의 기본 클래스에서 메서드를 상속할 수 있습니다, 되므로 개발자는 종종 지정된 된 메서드에 정의 되어 있는 클래스를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="e1406-125">`pstrClassName` 유효한 매개 변수를 가리키지 해야 `BSTR` 이기 때문에 함수를 호출 하기 전에 `out` 매개 변수;이 함수에서 반환 된 후 포인터 할당이 해제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1406-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1406-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1406-126">Requirements</span></span>  
<span data-ttu-id="e1406-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1406-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1406-128">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e1406-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e1406-129">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e1406-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1406-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1406-130">See also</span></span>

- [<span data-ttu-id="e1406-131">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="e1406-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
