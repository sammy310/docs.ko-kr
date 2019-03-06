---
title: ExecNotificationQueryWmi 함수 (관리 되지 않는 API 참조)
description: ExecNotificationQueryWmi 함수 이벤트를 수신 하는 쿼리를 실행 합니다.
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cac00ff96d0c7007bdd6135282c3f767217385e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352882"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="112d0-103">ExecNotificationQueryWmi 함수</span><span class="sxs-lookup"><span data-stu-id="112d0-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="112d0-104">쿼리를 실행하여 이벤트를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-104">Executes a query to receive events.</span></span> <span data-ttu-id="112d0-105">호출이 즉시 반환 하 고 호출자에 게 도착 했을 때 반환 된 이벤트에 대 한 열거자를 폴링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="112d0-106">쿼리를 취소 반환 된 열거자를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="112d0-107">구문</span><span class="sxs-lookup"><span data-stu-id="112d0-107">Syntax</span></span>

```cpp
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
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

## <a name="parameters"></a><span data-ttu-id="112d0-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="112d0-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="112d0-109">[in] Windows 관리를 지 원하는 올바른 쿼리 언어를 사용 하 여 사용 되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="112d0-110">WMI 쿼리 언어에 대 한 약칭 "WQL" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="112d0-111">[in] 쿼리의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-111">[in] The text of the query.</span></span> <span data-ttu-id="112d0-112">이 매개 변수 수 없습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="112d0-113">[in] 이 함수의 동작에 영향을 주는 두 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="112d0-114">이러한 값은 정의 된 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="112d0-115">상수</span><span class="sxs-lookup"><span data-stu-id="112d0-115">Constant</span></span> | <span data-ttu-id="112d0-116">값</span><span class="sxs-lookup"><span data-stu-id="112d0-116">Value</span></span>  | <span data-ttu-id="112d0-117">설명</span><span class="sxs-lookup"><span data-stu-id="112d0-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="112d0-118">0x10</span><span class="sxs-lookup"><span data-stu-id="112d0-118">0x10</span></span> | <span data-ttu-id="112d0-119">플래그를 사용 하면 일부 동기 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="112d0-120">이 플래그를 설정 하지 않으면 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="112d0-121">왜냐하면 이벤트가 지속적으로 수신 되는 사용자에 반환 된 열거자 폴링해야 합니다. 즉입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="112d0-122">이 호출을 무기한으로 차단 하면는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="112d0-123">0x20</span><span class="sxs-lookup"><span data-stu-id="112d0-123">0x20</span></span> | <span data-ttu-id="112d0-124">함수에는 정방향 전용 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="112d0-125">일반적으로 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 적은 메모리를 사용 하지만 호출을 허용 하지 않습니다 [복제](clone.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="112d0-126">[in] 이 값은 일반적으로 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="112d0-127">그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청된 이벤트를 제공 하는 공급자가 사용할 수 있는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="112d0-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="112d0-128">[out] 오류가 발생 하는 경우 호출자가 쿼리의 결과 집합의 인스턴스를 검색할 수 있도록 하는 열거자에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="112d0-129">참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="112d0-130">[in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="112d0-131">[in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="112d0-132">[in] 에 대 한 포인터를 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 현재 네임 스페이스를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="112d0-133">[in] 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-133">[in] The user name.</span></span> <span data-ttu-id="112d0-134">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="112d0-135">[in] 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-135">[in] The password.</span></span> <span data-ttu-id="112d0-136">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="112d0-137">[in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-137">[in] The domain name of the user.</span></span> <span data-ttu-id="112d0-138">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="112d0-139">반환 값</span><span class="sxs-lookup"><span data-stu-id="112d0-139">Return value</span></span>

<span data-ttu-id="112d0-140">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="112d0-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="112d0-141">상수</span><span class="sxs-lookup"><span data-stu-id="112d0-141">Constant</span></span>  |<span data-ttu-id="112d0-142">값</span><span class="sxs-lookup"><span data-stu-id="112d0-142">Value</span></span>  |<span data-ttu-id="112d0-143">설명</span><span class="sxs-lookup"><span data-stu-id="112d0-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="112d0-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="112d0-144">0x80041003</span></span> | <span data-ttu-id="112d0-145">사용자 함수를 반환할 수 있는 클래스 중 하나 이상을 볼 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="112d0-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="112d0-146">0x80041001</span></span> | <span data-ttu-id="112d0-147">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="112d0-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="112d0-148">0x80041008</span></span> | <span data-ttu-id="112d0-149">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="112d0-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="112d0-150">0x80041010</span></span> | <span data-ttu-id="112d0-151">쿼리는 존재 하지 않는 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="112d0-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="112d0-152">0x80042002</span></span> | <span data-ttu-id="112d0-153">이벤트 전달 정확 하 게 너무 많이 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="112d0-154">더 큰 폴링 허용 오차를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="112d0-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="112d0-155">0x80042001</span></span> | <span data-ttu-id="112d0-156">쿼리는 Windows 관리를 제공할 수 있습니다 보다 많은 정보를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="112d0-157">이 `HRESULT` 네임 스페이스의 모든 개체를 폴링 하려면 요청에서 이벤트 쿼리 결과 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="112d0-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="112d0-158">0x80041017</span></span> | <span data-ttu-id="112d0-159">쿼리 구문 오류가 발생을 했습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="112d0-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="112d0-160">0x80041018</span></span> | <span data-ttu-id="112d0-161">요청한 쿼리 언어는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="112d0-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="112d0-162">0x8004106c</span></span> | <span data-ttu-id="112d0-163">쿼리는 너무 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="112d0-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="112d0-164">0x80041006</span></span> | <span data-ttu-id="112d0-165">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="112d0-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="112d0-166">0x80041033</span></span> | <span data-ttu-id="112d0-167">WMI는 아마도 중지 및 다시 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="112d0-168">호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="112d0-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="112d0-169">0x80041015</span></span> | <span data-ttu-id="112d0-170">현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="112d0-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="112d0-171">0x80041058</span></span> | <span data-ttu-id="112d0-172">쿼리를 구문 분석할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="112d0-173">0</span><span class="sxs-lookup"><span data-stu-id="112d0-173">0</span></span> | <span data-ttu-id="112d0-174">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="112d0-175">설명</span><span class="sxs-lookup"><span data-stu-id="112d0-175">Remarks</span></span>

<span data-ttu-id="112d0-176">이 함수에 대 한 호출을 래핑하는 [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) 메서드.</span><span class="sxs-lookup"><span data-stu-id="112d0-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="112d0-177">함수가 반환 되 면 호출자가 정기적으로 전달할 반환 된 `ppEnum` 개체를 [다음](next.md) 함수를 사용할 수 있는 모든 이벤트.</span><span class="sxs-lookup"><span data-stu-id="112d0-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="112d0-178">수에 제한이 `AND` 및 `OR` WQL 쿼리에서 사용할 수 있는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="112d0-179">많은 복잡 한 쿼리를 사용 하는 WQL 키워드를 반환 하기 위해 WMI를 발생할 수 있습니다 합니다 `WBEM_E_QUOTA_VIOLATION` (또는 0x8004106c) 오류 코드는 `HRESULT` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="112d0-180">WQL 키워드 제한 방법을 복잡 한 쿼리는에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="112d0-181">함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="112d0-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="112d0-182">요구 사항</span><span class="sxs-lookup"><span data-stu-id="112d0-182">Requirements</span></span>

<span data-ttu-id="112d0-183">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="112d0-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="112d0-184">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="112d0-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="112d0-185">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="112d0-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="112d0-186">참고자료</span><span class="sxs-lookup"><span data-stu-id="112d0-186">See also</span></span>

- [<span data-ttu-id="112d0-187">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="112d0-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)