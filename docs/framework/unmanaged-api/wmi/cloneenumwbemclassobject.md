---
title: 클론에넘WbemClassObject 함수(관리되지 않는 API 참조)
description: CloneEnumWbemClassObject 함수는 열거자의 논리적 복사본을 만듭니다.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175020"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="ff326-103">CloneEnumWbemClassObject 함수</span><span class="sxs-lookup"><span data-stu-id="ff326-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="ff326-104">열거형의 현재 위치를 유지하면서 열거자의 논리적 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ff326-105">구문</span><span class="sxs-lookup"><span data-stu-id="ff326-105">Syntax</span></span>

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum,
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject,
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="ff326-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff326-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="ff326-107">【아웃】 새 [IEnumWbemClassObject에](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)대한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="ff326-108">【인】 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="ff326-109">【인】 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="ff326-110">【아웃】 복제할 [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="ff326-111">【인】 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-111">[in] The user name.</span></span> <span data-ttu-id="ff326-112">자세한 내용은 [ConnectServerWmi](connectserverwmi.md) 기능을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff326-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="ff326-113">【인】 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-113">[in] The password.</span></span> <span data-ttu-id="ff326-114">자세한 내용은 [ConnectServerWmi](connectserverwmi.md) 기능을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff326-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="ff326-115">【인】 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-115">[in] The domain name of the user.</span></span> <span data-ttu-id="ff326-116">자세한 내용은 [ConnectServerWmi](connectserverwmi.md) 기능을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff326-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="ff326-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="ff326-117">Return value</span></span>

<span data-ttu-id="ff326-118">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ff326-119">지속적임</span><span class="sxs-lookup"><span data-stu-id="ff326-119">Constant</span></span>  |<span data-ttu-id="ff326-120">값</span><span class="sxs-lookup"><span data-stu-id="ff326-120">Value</span></span>  |<span data-ttu-id="ff326-121">Description</span><span class="sxs-lookup"><span data-stu-id="ff326-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ff326-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ff326-122">0x80041001</span></span> | <span data-ttu-id="ff326-123">일반적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ff326-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ff326-124">0x80041008</span></span> | <span data-ttu-id="ff326-125">매개 변수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ff326-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ff326-126">0x80041006</span></span> | <span data-ttu-id="ff326-127">메모리가 부족하여 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ff326-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ff326-128">0x80041015</span></span> | <span data-ttu-id="ff326-129">현재 프로세스와 WMI 간의 원격 프로시저 호출(RPC) 연결이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ff326-130">0</span><span class="sxs-lookup"><span data-stu-id="ff326-130">0</span></span> | <span data-ttu-id="ff326-131">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ff326-132">설명</span><span class="sxs-lookup"><span data-stu-id="ff326-132">Remarks</span></span>

<span data-ttu-id="ff326-133">이 함수는 [IEnumWbemClassObject::복제](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="ff326-134">이 메서드는 "최선의 노력" 복사본만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="ff326-135">많은 CIM 개체의 동적 특성으로 인해 새 열거자가 원본 열거기와 동일한 개체 집합을 열거하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="ff326-136">함수 호출에 실패하면 [GetErrorInfo](geterrorinfo.md) 함수를 호출하여 추가 오류 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff326-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="ff326-137">예제</span><span class="sxs-lookup"><span data-stu-id="ff326-137">Example</span></span>

<span data-ttu-id="ff326-138">예를 들어 [IEnumWbemClassObject::복제](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) 메서드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff326-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff326-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff326-139">Requirements</span></span>
 <span data-ttu-id="ff326-140">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff326-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ff326-141">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ff326-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="ff326-142">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ff326-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ff326-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff326-143">See also</span></span>

- [<span data-ttu-id="ff326-144">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="ff326-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
