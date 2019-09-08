---
title: WritePropertyValue 함수 (관리 되지 않는 API 참조)
description: WritePropertyValue 함수는 속성에 바이트를 씁니다.
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3c42129835f9b30bed493a0992d49d7e2a458e2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798177"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="46c5c-103">WritePropertyValue 함수</span><span class="sxs-lookup"><span data-stu-id="46c5c-103">WritePropertyValue function</span></span>
<span data-ttu-id="46c5c-104">지정된 수의 바이트를 속성 핸들로 식별되는 속성에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="46c5c-105">구문</span><span class="sxs-lookup"><span data-stu-id="46c5c-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="46c5c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46c5c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="46c5c-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="46c5c-108">진행 [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="46c5c-109">진행 이 속성을 식별 하는 핸들을 포함 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="46c5c-110">[Getpropertyhandle](getpropertyhandle.md) 함수를 호출 하 여 핸들을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="46c5c-111">진행 속성에 기록 되는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="46c5c-112">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46c5c-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="46c5c-113">제한이 데이터를 포함 하는 바이트 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="46c5c-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="46c5c-114">Return value</span></span>

<span data-ttu-id="46c5c-115">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="46c5c-116">상수</span><span class="sxs-lookup"><span data-stu-id="46c5c-116">Constant</span></span>  |<span data-ttu-id="46c5c-117">값</span><span class="sxs-lookup"><span data-stu-id="46c5c-117">Value</span></span>  |<span data-ttu-id="46c5c-118">설명</span><span class="sxs-lookup"><span data-stu-id="46c5c-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="46c5c-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="46c5c-119">0x80041008</span></span> | <span data-ttu-id="46c5c-120">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="46c5c-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="46c5c-121">0x80041005</span></span> | <span data-ttu-id="46c5c-122">형식 불일치가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="46c5c-123">0</span><span class="sxs-lookup"><span data-stu-id="46c5c-123">0</span></span> | <span data-ttu-id="46c5c-124">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="46c5c-125">설명</span><span class="sxs-lookup"><span data-stu-id="46c5c-125">Remarks</span></span>

<span data-ttu-id="46c5c-126">이 함수는 [IWbemClassObject:: WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="46c5c-127">이 함수를 사용 하 여 문자열 및 기타`DWORD` `QWORD` 이외의 모든 데이터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="46c5c-128">문자열이 아닌 속성 값의 `lNumBytes` 경우는 지정 된 속성 형식의 올바른 데이터 크기 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="46c5c-129">문자열 속성 값의 경우 `lNumBytes` 는 지정 된 문자열의 길이 (바이트) 여야 하 고 문자열 자체는 짝수 길이 (바이트) 여야 하 고 null 종료 문자를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c5c-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="46c5c-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46c5c-130">Requirements</span></span>  
<span data-ttu-id="46c5c-131">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="46c5c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c5c-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="46c5c-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="46c5c-133">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="46c5c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c5c-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="46c5c-134">See also</span></span>

- [<span data-ttu-id="46c5c-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="46c5c-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
