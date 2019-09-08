---
title: GetPropertyHandle 함수 (관리 되지 않는 API 참조)
description: GetPropertyHandle 함수는 속성을 식별 하는 고유 핸들을 반환 합니다.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d72b0da43971a74a08a249b19dfc0d446eeb5e6a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798548"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="b37c3-103">GetPropertyHandle 함수</span><span class="sxs-lookup"><span data-stu-id="b37c3-103">GetPropertyHandle function</span></span>

<span data-ttu-id="b37c3-104">속성을 식별하는 고유한 핸들을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b37c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="b37c3-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="b37c3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b37c3-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="b37c3-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="b37c3-108">진행 [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="b37c3-109">진행 속성 이름을 포함 하는 UTF16 인코딩된 문자를 포함 하는 null로 끝나는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="b37c3-110">제한이 속성의 CIM 형식을 [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) 나타내는 열거형 멤버에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-110">[out] A pointer to a [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="b37c3-111">제한이 속성 핸들을 포함 하는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="b37c3-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="b37c3-112">Return value</span></span>

<span data-ttu-id="b37c3-113">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b37c3-114">상수</span><span class="sxs-lookup"><span data-stu-id="b37c3-114">Constant</span></span>  |<span data-ttu-id="b37c3-115">값</span><span class="sxs-lookup"><span data-stu-id="b37c3-115">Value</span></span>  |<span data-ttu-id="b37c3-116">Description</span><span class="sxs-lookup"><span data-stu-id="b37c3-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="b37c3-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b37c3-117">0x80041002</span></span> | <span data-ttu-id="b37c3-118">지정 된 속성 이름을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b37c3-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b37c3-119">0x80041008</span></span> | <span data-ttu-id="b37c3-120">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="b37c3-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="b37c3-121">0x8004100c</span></span> | <span data-ttu-id="b37c3-122">요청 된 속성이 `CIM_OBJECT` 또는 `CIM_ARRAY`형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b37c3-123">0</span><span class="sxs-lookup"><span data-stu-id="b37c3-123">0</span></span> | <span data-ttu-id="b37c3-124">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b37c3-125">설명</span><span class="sxs-lookup"><span data-stu-id="b37c3-125">Remarks</span></span>

<span data-ttu-id="b37c3-126">이 함수는 [IWbemClassObject:: GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="b37c3-127">[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) 메서드를 사용 하 여 속성 값을 읽거나 쓸 때이 핸들을 사용 하 여 속성을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="b37c3-128">`CIM_OBJECT` 및`CIM_ARRAY`이외의 모든 데이터 형식의 속성에 대해 핸들을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="b37c3-129">반환 된 핸들은 클래스의 모든 인스턴스에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b37c3-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="b37c3-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b37c3-130">Requirements</span></span>

<span data-ttu-id="b37c3-131">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b37c3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b37c3-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b37c3-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b37c3-133">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b37c3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b37c3-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="b37c3-134">See also</span></span>

- [<span data-ttu-id="b37c3-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b37c3-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
