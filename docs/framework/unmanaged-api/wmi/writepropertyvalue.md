---
title: WritePropertyValue 함수(관리되지 않는 API 참조)
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174838"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="ec01a-103">WritePropertyValue 함수</span><span class="sxs-lookup"><span data-stu-id="ec01a-103">WritePropertyValue function</span></span>
<span data-ttu-id="ec01a-104">지정된 수의 바이트를 속성 핸들로 식별되는 속성에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ec01a-105">구문</span><span class="sxs-lookup"><span data-stu-id="ec01a-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
);
```  

## <a name="parameters"></a><span data-ttu-id="ec01a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec01a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ec01a-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ec01a-108">【인】 [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="ec01a-109">【인】 이 속성을 식별하는 핸들을 포함하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="ec01a-110">[GetPropertyHandle](getpropertyhandle.md) 함수를 호출하여 핸들을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>

`lNumBytes`  
<span data-ttu-id="ec01a-111">【인】 속성에 기록되는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="ec01a-112">자세한 내용은 [비고](#remarks) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec01a-112">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="ec01a-113">`pHandle`【아웃】 데이터를 포함하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-113">`pHandle` [out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="ec01a-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="ec01a-114">Return value</span></span>

<span data-ttu-id="ec01a-115">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ec01a-116">지속적임</span><span class="sxs-lookup"><span data-stu-id="ec01a-116">Constant</span></span>  |<span data-ttu-id="ec01a-117">값</span><span class="sxs-lookup"><span data-stu-id="ec01a-117">Value</span></span>  |<span data-ttu-id="ec01a-118">Description</span><span class="sxs-lookup"><span data-stu-id="ec01a-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ec01a-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ec01a-119">0x80041008</span></span> | <span data-ttu-id="ec01a-120">매개 변수가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="ec01a-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="ec01a-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="ec01a-121">0x80041005</span></span> | <span data-ttu-id="ec01a-122">형식이 맞지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="ec01a-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ec01a-123">0</span><span class="sxs-lookup"><span data-stu-id="ec01a-123">0</span></span> | <span data-ttu-id="ec01a-124">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ec01a-125">설명</span><span class="sxs-lookup"><span data-stu-id="ec01a-125">Remarks</span></span>

<span data-ttu-id="ec01a-126">이 함수는 [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="ec01a-127">이 함수를 사용하여 문자열 및`DWORD` 기타 모든`QWORD` 비데이터 또는 비데이터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="ec01a-128">비string 속성 값의 경우 지정된 속성 형식의 올바른 데이터 `lNumBytes` 크기여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="ec01a-129">string 속성 값의 `lNumBytes` 경우 지정된 문자열의 길이바이트여야 하며 문자열 자체는 바이트의 짝수 길이여야 하며 null-termination 문자가 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec01a-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="ec01a-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec01a-130">Requirements</span></span>  
<span data-ttu-id="ec01a-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec01a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec01a-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ec01a-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ec01a-133">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ec01a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec01a-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec01a-134">See also</span></span>

- [<span data-ttu-id="ec01a-135">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="ec01a-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
