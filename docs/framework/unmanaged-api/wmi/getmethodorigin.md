---
title: GetMethodOrigin 함수 (관리 되지 않는 API 참조)
description: GetMethodOrigin 함수는 메서드가 선언 되는 클래스를 결정 합니다.
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
ms.openlocfilehash: 1f669d5721a7bd9434f0ce4b1e2290c0633e1b46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102541"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="89c81-103">GetMethodOrigin 함수</span><span class="sxs-lookup"><span data-stu-id="89c81-103">GetMethodOrigin function</span></span>
<span data-ttu-id="89c81-104">메서드가 선언되는 클래스를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="89c81-105">구문</span><span class="sxs-lookup"><span data-stu-id="89c81-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="89c81-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89c81-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="89c81-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="89c81-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="89c81-109">진행 소유 하는 클래스가 요청 된 개체의 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="89c81-110">제한이 메서드를 소유 하는 클래스의 이름을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="89c81-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="89c81-111">Return value</span></span>

<span data-ttu-id="89c81-112">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="89c81-113">상수</span><span class="sxs-lookup"><span data-stu-id="89c81-113">Constant</span></span>  |<span data-ttu-id="89c81-114">값</span><span class="sxs-lookup"><span data-stu-id="89c81-114">Value</span></span>  |<span data-ttu-id="89c81-115">설명</span><span class="sxs-lookup"><span data-stu-id="89c81-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="89c81-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="89c81-116">0x80041002</span></span> | <span data-ttu-id="89c81-117">지정 된 메서드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="89c81-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="89c81-118">0x80041008</span></span> | <span data-ttu-id="89c81-119">하나 이상의 매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="89c81-120">0</span><span class="sxs-lookup"><span data-stu-id="89c81-120">0</span></span> | <span data-ttu-id="89c81-121">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="89c81-122">주의</span><span class="sxs-lookup"><span data-stu-id="89c81-122">Remarks</span></span>

<span data-ttu-id="89c81-123">이 함수는 [IWbemClassObject:: GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="89c81-124">클래스는 하나 이상의 기본 클래스에서 메서드를 상속할 수 있기 때문에 일반적으로 개발자는 지정 된 메서드가 정의 된 클래스를 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="89c81-125">`pstrClassName` 매개 변수는 `out` 매개 변수 이므로 함수를 호출 하기 전에 유효한 `BSTR`을 가리키지 않아야 합니다. 함수가 반환 된 후에는이 포인터가 할당 취소 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89c81-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="89c81-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89c81-126">Requirements</span></span>  
<span data-ttu-id="89c81-127">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89c81-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89c81-128">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="89c81-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="89c81-129">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="89c81-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c81-130">참조</span><span class="sxs-lookup"><span data-stu-id="89c81-130">See also</span></span>

- [<span data-ttu-id="89c81-131">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="89c81-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
