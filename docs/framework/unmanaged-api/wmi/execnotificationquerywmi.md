---
title: ExecNotificationQueryWmi 함수 (관리 되지 않는 API 참조)
description: ExecNotificationQueryWmi 함수는 쿼리를 실행 하 여 이벤트를 수신 합니다.
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
ms.openlocfilehash: 3d8a7683eef52a5e91bf7aa84d5aa7db7dbdac8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130445"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="0d82b-103">ExecNotificationQueryWmi 함수</span><span class="sxs-lookup"><span data-stu-id="0d82b-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="0d82b-104">쿼리를 실행하여 이벤트를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-104">Executes a query to receive events.</span></span> <span data-ttu-id="0d82b-105">호출은 즉시 반환 되며 호출자는 도착 시 이벤트에 대해 반환 된 열거자를 폴링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="0d82b-106">반환 된 열거자를 해제 하면 쿼리가 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0d82b-107">구문</span><span class="sxs-lookup"><span data-stu-id="0d82b-107">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="0d82b-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d82b-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="0d82b-109">진행 Windows Management에서 지 원하는 유효한 쿼리 언어를 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="0d82b-110">WQL(WMI Query Language)에 대 한 머리글자어 인 "WQL" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="0d82b-111">진행 쿼리 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-111">[in] The text of the query.</span></span> <span data-ttu-id="0d82b-112">이 매개 변수를 `null`수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="0d82b-113">진행 이 함수의 동작에 영향을 주는 다음 두 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="0d82b-114">이러한 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="0d82b-115">상수</span><span class="sxs-lookup"><span data-stu-id="0d82b-115">Constant</span></span> | <span data-ttu-id="0d82b-116">값</span><span class="sxs-lookup"><span data-stu-id="0d82b-116">Value</span></span>  | <span data-ttu-id="0d82b-117">설명</span><span class="sxs-lookup"><span data-stu-id="0d82b-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="0d82b-118">0x10</span><span class="sxs-lookup"><span data-stu-id="0d82b-118">0x10</span></span> | <span data-ttu-id="0d82b-119">플래그는 동기 호출을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="0d82b-120">이 플래그를 설정 하지 않으면 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="0d82b-121">이는 이벤트가 지속적으로 수신 되기 때문입니다. 즉, 사용자가 반환 된 열거자를 폴링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="0d82b-122">이 호출을 무기한 차단 하면 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="0d82b-123">0x20</span><span class="sxs-lookup"><span data-stu-id="0d82b-123">0x20</span></span> | <span data-ttu-id="0d82b-124">함수는 앞 으로만 이동 가능한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="0d82b-125">일반적으로 앞 으로만 이동 가능한 열거자는 기존 열거자 보다 더 빠르고 메모리를 사용 하지만, 이러한 열거자는 호출을 [복제할](clone.md)수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="0d82b-126">진행 일반적으로이 값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="0d82b-127">그렇지 않으면 요청 된 이벤트를 제공 하는 공급자가 사용할 수 있는 [iwbemcontext 개체가 올바르지](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="0d82b-128">제한이 오류가 발생 하지 않으면는 호출자가 쿼리의 결과 집합에서 인스턴스를 검색할 수 있도록 열거자에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="0d82b-129">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d82b-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="0d82b-130">진행 권한 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="0d82b-131">진행 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="0d82b-132">진행 현재 네임 스페이스를 나타내는 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="0d82b-133">진행 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-133">[in] The user name.</span></span> <span data-ttu-id="0d82b-134">자세한 내용은 [Connectserverwmi](connectserverwmi.md) 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d82b-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="0d82b-135">진행 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-135">[in] The password.</span></span> <span data-ttu-id="0d82b-136">자세한 내용은 [Connectserverwmi](connectserverwmi.md) 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d82b-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="0d82b-137">진행 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-137">[in] The domain name of the user.</span></span> <span data-ttu-id="0d82b-138">자세한 내용은 [Connectserverwmi](connectserverwmi.md) 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d82b-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="0d82b-139">반환 값</span><span class="sxs-lookup"><span data-stu-id="0d82b-139">Return value</span></span>

<span data-ttu-id="0d82b-140">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0d82b-141">상수</span><span class="sxs-lookup"><span data-stu-id="0d82b-141">Constant</span></span>  |<span data-ttu-id="0d82b-142">값</span><span class="sxs-lookup"><span data-stu-id="0d82b-142">Value</span></span>  |<span data-ttu-id="0d82b-143">설명</span><span class="sxs-lookup"><span data-stu-id="0d82b-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="0d82b-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="0d82b-144">0x80041003</span></span> | <span data-ttu-id="0d82b-145">사용자에 게 함수가 반환할 수 있는 하나 이상의 클래스를 볼 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="0d82b-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0d82b-146">0x80041001</span></span> | <span data-ttu-id="0d82b-147">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0d82b-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0d82b-148">0x80041008</span></span> | <span data-ttu-id="0d82b-149">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="0d82b-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="0d82b-150">0x80041010</span></span> | <span data-ttu-id="0d82b-151">쿼리에서 존재 하지 않는 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="0d82b-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="0d82b-152">0x80042002</span></span> | <span data-ttu-id="0d82b-153">너무 많은 이벤트 배달이 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="0d82b-154">더 큰 폴링 허용 시간을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="0d82b-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="0d82b-155">0x80042001</span></span> | <span data-ttu-id="0d82b-156">이 쿼리는 Windows Management가 제공할 수 있는 것 보다 많은 정보를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="0d82b-157">이 `HRESULT`는 이벤트 쿼리가 네임 스페이스의 모든 개체를 폴링하는 요청을 발생 시킬 때 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="0d82b-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="0d82b-158">0x80041017</span></span> | <span data-ttu-id="0d82b-159">쿼리에 구문 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="0d82b-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="0d82b-160">0x80041018</span></span> | <span data-ttu-id="0d82b-161">요청한 쿼리 언어는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="0d82b-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="0d82b-162">0x8004106c</span></span> | <span data-ttu-id="0d82b-163">쿼리가 너무 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0d82b-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0d82b-164">0x80041006</span></span> | <span data-ttu-id="0d82b-165">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="0d82b-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="0d82b-166">0x80041033</span></span> | <span data-ttu-id="0d82b-167">WMI가 중지 되었다가 다시 시작 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="0d82b-168">[Connectserverwmi](connectserverwmi.md) 를 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="0d82b-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="0d82b-169">0x80041015</span></span> | <span data-ttu-id="0d82b-170">현재 프로세스와 WMI 간의 RPC (원격 프로시저 호출) 링크에 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="0d82b-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="0d82b-171">0x80041058</span></span> | <span data-ttu-id="0d82b-172">쿼리를 구문 분석할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0d82b-173">0</span><span class="sxs-lookup"><span data-stu-id="0d82b-173">0</span></span> | <span data-ttu-id="0d82b-174">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0d82b-175">주의</span><span class="sxs-lookup"><span data-stu-id="0d82b-175">Remarks</span></span>

<span data-ttu-id="0d82b-176">이 함수는 [IWbemServices:: ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="0d82b-177">함수가 반환 된 후 호출자는 반환 된 `ppEnum` 개체를 [다음](next.md) 함수에 주기적으로 전달 하 여 사용 가능한 이벤트가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="0d82b-178">WQL 쿼리에서 사용할 수 있는 `AND` 및 `OR` 키워드 수에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="0d82b-179">복잡 한 쿼리에 사용 되는 WQL 키워드가 많은 경우 WMI가 `WBEM_E_QUOTA_VIOLATION` (또는 0x8004106c) 오류 코드를 `HRESULT` 값으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="0d82b-180">WQL 키워드의 제한은 쿼리의 복잡 한 정도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="0d82b-181">함수 호출이 실패 하면 [Geterrorinfo](geterrorinfo.md) 함수를 호출 하 여 추가 오류 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d82b-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="0d82b-182">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d82b-182">Requirements</span></span>

<span data-ttu-id="0d82b-183">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d82b-183">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0d82b-184">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="0d82b-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="0d82b-185">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0d82b-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0d82b-186">참조</span><span class="sxs-lookup"><span data-stu-id="0d82b-186">See also</span></span>

- [<span data-ttu-id="0d82b-187">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="0d82b-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
