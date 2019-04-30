---
title: CreateInstanceEnumWmi 함수 (관리 되지 않는 API 참조)
description: CreateInstanceEnumWmi 함수 선택 조건을 충족 하는 지정된 된 클래스의 인스턴스를 포함 하는 열거자를 반환 합니다.
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a1d082cae19bd83c90e063d841a0c9e4602bc40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040705"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="1811b-103">CreateInstanceEnumWmi 함수</span><span class="sxs-lookup"><span data-stu-id="1811b-103">CreateInstanceEnumWmi function</span></span>

<span data-ttu-id="1811b-104">지정된 선택 조건을 충족하는 지정된 클래스의 인스턴스를 반환하는 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1811b-105">구문</span><span class="sxs-lookup"><span data-stu-id="1811b-105">Syntax</span></span>

```cpp
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="1811b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1811b-106">Parameters</span></span>

`strFilter`\
<span data-ttu-id="1811b-107">[in] 인스턴스는 필요한 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="1811b-108">이 매개 변수 수 없습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-108">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="1811b-109">[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="1811b-110">에 정의 된 다음 값을 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="1811b-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1811b-111">상수</span><span class="sxs-lookup"><span data-stu-id="1811b-111">Constant</span></span>  |<span data-ttu-id="1811b-112">값</span><span class="sxs-lookup"><span data-stu-id="1811b-112">Value</span></span>  |<span data-ttu-id="1811b-113">설명</span><span class="sxs-lookup"><span data-stu-id="1811b-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="1811b-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="1811b-114">0x20000</span></span> | <span data-ttu-id="1811b-115">경우 집합 함수는 현재 연결의 로캘의 지역화 된 네임 스페이스에 저장 된 수정 된 한정자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="1811b-116">그렇지 않은 경우 집합 함수를 즉시 네임 스페이스에 저장 된 한정자만 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="1811b-117">0</span><span class="sxs-lookup"><span data-stu-id="1811b-117">0</span></span> | <span data-ttu-id="1811b-118">계층 구조에서이 및 모든 하위 클래스를 포함 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="1811b-119">1</span><span class="sxs-lookup"><span data-stu-id="1811b-119">1</span></span> | <span data-ttu-id="1811b-120">이 클래스의 순수 인스턴스만 포함이 클래스에 없는 속성을 제공 하는 서브 클래스의 모든 인스턴스를 제외 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="1811b-121">0x10</span><span class="sxs-lookup"><span data-stu-id="1811b-121">0x10</span></span> | <span data-ttu-id="1811b-122">플래그를 사용 하면 일부 동기 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="1811b-123">0x20</span><span class="sxs-lookup"><span data-stu-id="1811b-123">0x20</span></span> | <span data-ttu-id="1811b-124">함수에는 정방향 전용 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="1811b-125">일반적으로 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 적은 메모리를 사용 하지만 호출을 허용 하지 않습니다 [복제](clone.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="1811b-126">0</span><span class="sxs-lookup"><span data-stu-id="1811b-126">0</span></span> | <span data-ttu-id="1811b-127">WMI가 릴리스될 때까지 열거형에는 개체에 대 한 포인터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-127">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="1811b-128">권장 되는 플래그가 `WBEM_FLAG_RETURN_IMMEDIATELY` 고 `WBEM_FLAG_FORWARD_ONLY` 최상의 성능을 위해.</span><span class="sxs-lookup"><span data-stu-id="1811b-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="1811b-129">[in] 이 값은 일반적으로 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="1811b-130">그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청된 인스턴스를 제공 하는 공급자가 사용할 수 있는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="1811b-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`\
<span data-ttu-id="1811b-131">[out] 열거자에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="1811b-132">[in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-132">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="1811b-133">[in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-133">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="1811b-134">[in] 에 대 한 포인터를 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 현재 네임 스페이스를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="1811b-135">[in] 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-135">[in] The user name.</span></span> <span data-ttu-id="1811b-136">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="1811b-137">[in] 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-137">[in] The password.</span></span> <span data-ttu-id="1811b-138">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="1811b-139">[in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-139">[in] The domain name of the user.</span></span> <span data-ttu-id="1811b-140">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="1811b-141">반환 값</span><span class="sxs-lookup"><span data-stu-id="1811b-141">Return value</span></span>

<span data-ttu-id="1811b-142">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="1811b-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1811b-143">상수</span><span class="sxs-lookup"><span data-stu-id="1811b-143">Constant</span></span>  |<span data-ttu-id="1811b-144">값</span><span class="sxs-lookup"><span data-stu-id="1811b-144">Value</span></span>  |<span data-ttu-id="1811b-145">설명</span><span class="sxs-lookup"><span data-stu-id="1811b-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="1811b-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="1811b-146">0x80041003</span></span> | <span data-ttu-id="1811b-147">사용자 지정된 클래스의 인스턴스를 볼 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="1811b-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1811b-148">0x80041001</span></span> | <span data-ttu-id="1811b-149">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="1811b-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="1811b-150">0x80041010</span></span> | <span data-ttu-id="1811b-151">`strFilter`가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="1811b-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1811b-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1811b-152">0x80041008</span></span> | <span data-ttu-id="1811b-153">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1811b-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1811b-154">0x80041006</span></span> | <span data-ttu-id="1811b-155">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="1811b-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="1811b-156">0x80041033</span></span> | <span data-ttu-id="1811b-157">WMI는 아마도 중지 및 다시 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="1811b-158">호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="1811b-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="1811b-159">0x80041015</span></span> | <span data-ttu-id="1811b-160">현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1811b-161">0</span><span class="sxs-lookup"><span data-stu-id="1811b-161">0</span></span> | <span data-ttu-id="1811b-162">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-162">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="1811b-163">설명</span><span class="sxs-lookup"><span data-stu-id="1811b-163">Remarks</span></span>

<span data-ttu-id="1811b-164">이 함수에 대 한 호출을 래핑하는 [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) 메서드.</span><span class="sxs-lookup"><span data-stu-id="1811b-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="1811b-165">참고 반환 된 열거자가 0 개 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="1811b-166">함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1811b-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="1811b-167">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1811b-167">Requirements</span></span>

<span data-ttu-id="1811b-168">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1811b-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="1811b-169">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1811b-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="1811b-170">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1811b-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1811b-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="1811b-171">See also</span></span>

- [<span data-ttu-id="1811b-172">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="1811b-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)