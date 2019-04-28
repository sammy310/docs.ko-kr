---
title: ExecQueryWmi 함수 (관리 되지 않는 API 참조)
description: ExecQueryWmi 함수 개체를 검색 하는 쿼리를 실행 합니다.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 402bbcb9ad5e462a55c5ec2716417f512f03ee19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609063"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="30ffc-103">ExecQueryWmi 함수</span><span class="sxs-lookup"><span data-stu-id="30ffc-103">ExecQueryWmi function</span></span>

<span data-ttu-id="30ffc-104">쿼리를 실행하여 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="30ffc-105">구문</span><span class="sxs-lookup"><span data-stu-id="30ffc-105">Syntax</span></span>

```cpp
HRESULT ExecQueryWmi (
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

## <a name="parameters"></a><span data-ttu-id="30ffc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30ffc-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="30ffc-107">[in] Windows 관리를 지 원하는 올바른 쿼리 언어를 사용 하 여 사용 되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="30ffc-108">WMI 쿼리 언어에 대 한 약칭 "WQL" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="30ffc-109">[in] 쿼리의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-109">[in] The text of the query.</span></span> <span data-ttu-id="30ffc-110">이 매개 변수 수 없습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="30ffc-111">[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="30ffc-112">에 정의 된 다음 값을 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="30ffc-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="30ffc-113">상수</span><span class="sxs-lookup"><span data-stu-id="30ffc-113">Constant</span></span> | <span data-ttu-id="30ffc-114">값</span><span class="sxs-lookup"><span data-stu-id="30ffc-114">Value</span></span>  | <span data-ttu-id="30ffc-115">설명</span><span class="sxs-lookup"><span data-stu-id="30ffc-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="30ffc-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="30ffc-116">0x20000</span></span> | <span data-ttu-id="30ffc-117">경우 집합 함수는 현재 연결의 로캘의 지역화 된 네임 스페이스에 저장 된 수정 된 한정자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="30ffc-118">그렇지 않은 경우 집합 함수를 즉시 네임 스페이스에 저장 된 한정자만 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="30ffc-119">0x10</span><span class="sxs-lookup"><span data-stu-id="30ffc-119">0x10</span></span> | <span data-ttu-id="30ffc-120">플래그를 사용 하면 일부 동기 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="30ffc-121">0x20</span><span class="sxs-lookup"><span data-stu-id="30ffc-121">0x20</span></span> | <span data-ttu-id="30ffc-122">함수에는 정방향 전용 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="30ffc-123">일반적으로 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 적은 메모리를 사용 하지만 호출을 허용 하지 않습니다 [복제](clone.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="30ffc-124">0</span><span class="sxs-lookup"><span data-stu-id="30ffc-124">0</span></span> | <span data-ttu-id="30ffc-125">WMI가 릴리스될 때까지 열거형에는 개체에 대 한 포인터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="30ffc-126">0x100</span><span class="sxs-lookup"><span data-stu-id="30ffc-126">0x100</span></span> | <span data-ttu-id="30ffc-127">반환 된 모든 개체에 따라서 충분 한 정보가 포함 하면 해당 시스템 속성을 같은 **__PATH**를 **__RELPATH**, 및 **__SERVER**, 되지 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="30ffc-128">2</span><span class="sxs-lookup"><span data-stu-id="30ffc-128">2</span></span> | <span data-ttu-id="30ffc-129">이 플래그는 프로토타이핑에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-129">This flag is used for prototyping.</span></span> <span data-ttu-id="30ffc-130">쿼리를 실행 하지 않습니다 하 고 대신 일반적인 결과 개체를 같은 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="30ffc-131">0x200</span><span class="sxs-lookup"><span data-stu-id="30ffc-131">0x200</span></span> | <span data-ttu-id="30ffc-132">원인 직접 부모 클래스 또는 서브 클래스에 관계 없이 지정 된 클래스에 대 한 공급자에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="30ffc-133">권장 되는 플래그가 `WBEM_FLAG_RETURN_IMMEDIATELY` 고 `WBEM_FLAG_FORWARD_ONLY` 최상의 성능을 위해.</span><span class="sxs-lookup"><span data-stu-id="30ffc-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="30ffc-134">[in] 이 값은 일반적으로 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="30ffc-135">그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="30ffc-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="30ffc-136">[out] 오류가 발생 하는 경우 호출자가 쿼리의 결과 집합의 인스턴스를 검색할 수 있도록 하는 열거자에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="30ffc-137">쿼리 결과 0 인스턴스를 사용 하 여 집합에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="30ffc-138">참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="30ffc-139">[in] 권한 부여 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="30ffc-140">[in] 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="30ffc-141">[in] 에 대 한 포인터를 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 현재 네임 스페이스를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="30ffc-142">[in] 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-142">[in] The user name.</span></span> <span data-ttu-id="30ffc-143">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="30ffc-144">[in] 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-144">[in] The password.</span></span> <span data-ttu-id="30ffc-145">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="30ffc-146">[in] 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-146">[in] The domain name of the user.</span></span> <span data-ttu-id="30ffc-147">참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="30ffc-148">반환 값</span><span class="sxs-lookup"><span data-stu-id="30ffc-148">Return value</span></span>

<span data-ttu-id="30ffc-149">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="30ffc-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="30ffc-150">상수</span><span class="sxs-lookup"><span data-stu-id="30ffc-150">Constant</span></span>  |<span data-ttu-id="30ffc-151">값</span><span class="sxs-lookup"><span data-stu-id="30ffc-151">Value</span></span>  |<span data-ttu-id="30ffc-152">설명</span><span class="sxs-lookup"><span data-stu-id="30ffc-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="30ffc-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="30ffc-153">0x80041003</span></span> | <span data-ttu-id="30ffc-154">사용자 함수를 반환할 수 있는 클래스 중 하나 이상을 볼 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="30ffc-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="30ffc-155">0x80041001</span></span> | <span data-ttu-id="30ffc-156">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="30ffc-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="30ffc-157">0x80041008</span></span> | <span data-ttu-id="30ffc-158">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="30ffc-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="30ffc-159">0x80041017</span></span> | <span data-ttu-id="30ffc-160">쿼리 구문 오류가 발생을 했습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="30ffc-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="30ffc-161">0x80041018</span></span> | <span data-ttu-id="30ffc-162">요청한 쿼리 언어는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="30ffc-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="30ffc-163">0x8004106c</span></span> | <span data-ttu-id="30ffc-164">쿼리는 너무 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="30ffc-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="30ffc-165">0x80041006</span></span> | <span data-ttu-id="30ffc-166">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="30ffc-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="30ffc-167">0x80041033</span></span> | <span data-ttu-id="30ffc-168">WMI는 아마도 중지 및 다시 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="30ffc-169">호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="30ffc-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="30ffc-170">0x80041015</span></span> | <span data-ttu-id="30ffc-171">현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="30ffc-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="30ffc-172">0x80041002</span></span> | <span data-ttu-id="30ffc-173">쿼리는 존재 하지 않는 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="30ffc-174">0</span><span class="sxs-lookup"><span data-stu-id="30ffc-174">0</span></span> | <span data-ttu-id="30ffc-175">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="30ffc-176">설명</span><span class="sxs-lookup"><span data-stu-id="30ffc-176">Remarks</span></span>

<span data-ttu-id="30ffc-177">이 함수에 대 한 호출을 래핑하는 [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) 메서드.</span><span class="sxs-lookup"><span data-stu-id="30ffc-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="30ffc-178">이 함수에 지정 된 쿼리를 처리는 `strQuery` 매개 변수는 호출자가 쿼리 결과 액세스할 수는 열거자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="30ffc-179">열거자에 대 한 포인터는는 [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) 인터페이스; 쿼리 결과가 통해 사용할 수 있는 클래스 개체의 인스턴스를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="30ffc-180">수에 제한이 `AND` 및 `OR` WQL 쿼리에서 사용할 수 있는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="30ffc-181">많은 복잡 한 쿼리를 사용 하는 WQL 키워드를 반환 하기 위해 WMI를 발생할 수 있습니다 합니다 `WBEM_E_QUOTA_VIOLATION` (또는 0x8004106c) 오류 코드는 `HRESULT` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="30ffc-182">WQL 키워드 제한 방법을 복잡 한 쿼리는에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="30ffc-183">함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="30ffc-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="30ffc-184">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30ffc-184">Requirements</span></span>

<span data-ttu-id="30ffc-185">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="30ffc-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="30ffc-186">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="30ffc-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="30ffc-187">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="30ffc-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="30ffc-188">참고자료</span><span class="sxs-lookup"><span data-stu-id="30ffc-188">See also</span></span>

- [<span data-ttu-id="30ffc-189">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="30ffc-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)