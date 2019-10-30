---
title: ExecQueryWmi 함수 (관리 되지 않는 API 참조)
description: ExecQueryWmi 함수는 개체를 검색 하는 쿼리를 실행 합니다.
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
ms.openlocfilehash: 3c6ea58eca5ac635893a24b57ade261e04a69721
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130429"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="f0c67-103">ExecQueryWmi 함수</span><span class="sxs-lookup"><span data-stu-id="f0c67-103">ExecQueryWmi function</span></span>

<span data-ttu-id="f0c67-104">쿼리를 실행하여 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f0c67-105">구문</span><span class="sxs-lookup"><span data-stu-id="f0c67-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="f0c67-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0c67-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="f0c67-107">진행 Windows Management에서 지 원하는 유효한 쿼리 언어를 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="f0c67-108">WQL(WMI Query Language)에 대 한 머리글자어 인 "WQL" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="f0c67-109">진행 쿼리 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-109">[in] The text of the query.</span></span> <span data-ttu-id="f0c67-110">이 매개 변수를 `null`수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="f0c67-111">진행 이 함수의 동작에 영향을 주는 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="f0c67-112">다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="f0c67-113">상수</span><span class="sxs-lookup"><span data-stu-id="f0c67-113">Constant</span></span> | <span data-ttu-id="f0c67-114">값</span><span class="sxs-lookup"><span data-stu-id="f0c67-114">Value</span></span>  | <span data-ttu-id="f0c67-115">설명</span><span class="sxs-lookup"><span data-stu-id="f0c67-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="f0c67-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="f0c67-116">0x20000</span></span> | <span data-ttu-id="f0c67-117">설정 하는 경우 함수는 현재 연결 로캘의 지역화 된 네임 스페이스에 저장 된 수정 된 한정자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="f0c67-118">설정 되지 않은 경우 함수는 직접 실행 네임 스페이스에 저장 된 한정자만 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="f0c67-119">0x10</span><span class="sxs-lookup"><span data-stu-id="f0c67-119">0x10</span></span> | <span data-ttu-id="f0c67-120">플래그는 동기 호출을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="f0c67-121">0x20</span><span class="sxs-lookup"><span data-stu-id="f0c67-121">0x20</span></span> | <span data-ttu-id="f0c67-122">함수는 앞 으로만 이동 가능한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="f0c67-123">일반적으로 앞 으로만 이동 가능한 열거자는 기존 열거자 보다 더 빠르고 메모리를 사용 하지만, 이러한 열거자는 호출을 [복제할](clone.md)수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="f0c67-124">0</span><span class="sxs-lookup"><span data-stu-id="f0c67-124">0</span></span> | <span data-ttu-id="f0c67-125">WMI는 해제할 때까지 열거형의 개체에 대 한 포인터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="f0c67-126">0x100</span><span class="sxs-lookup"><span data-stu-id="f0c67-126">0x100</span></span> | <span data-ttu-id="f0c67-127">**__Path**, **__RELPATH**, **__path**등의 시스템 속성이 `null`되지 않도록 반환 된 개체에 충분 한 정보가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="f0c67-128">2</span><span class="sxs-lookup"><span data-stu-id="f0c67-128">2</span></span> | <span data-ttu-id="f0c67-129">이 플래그는 프로토타입 생성에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-129">This flag is used for prototyping.</span></span> <span data-ttu-id="f0c67-130">쿼리를 실행 하지 않고 대신 일반적인 결과 개체 처럼 보이는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="f0c67-131">0x200</span><span class="sxs-lookup"><span data-stu-id="f0c67-131">0x200</span></span> | <span data-ttu-id="f0c67-132">부모 클래스 또는 서브 클래스에 관계 없이 지정 된 클래스에 대 한 공급자에 게 직접 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="f0c67-133">권장 플래그는 `WBEM_FLAG_RETURN_IMMEDIATELY` 하 고 최상의 성능을 위해 `WBEM_FLAG_FORWARD_ONLY` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="f0c67-134">진행 일반적으로이 값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="f0c67-135">그렇지 않으면 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 [iwbemcontext 개체가 올바르지](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="f0c67-136">제한이 오류가 발생 하지 않으면는 호출자가 쿼리의 결과 집합에서 인스턴스를 검색할 수 있도록 열거자에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="f0c67-137">이 쿼리는 인스턴스를 포함 하는 결과 집합을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="f0c67-138">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c67-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="f0c67-139">진행 권한 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="f0c67-140">진행 가장 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="f0c67-141">진행 현재 네임 스페이스를 나타내는 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="f0c67-142">진행 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-142">[in] The user name.</span></span> <span data-ttu-id="f0c67-143">자세한 내용은 [Connectserverwmi](connectserverwmi.md) 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c67-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="f0c67-144">진행 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-144">[in] The password.</span></span> <span data-ttu-id="f0c67-145">자세한 내용은 [Connectserverwmi](connectserverwmi.md) 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c67-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="f0c67-146">진행 사용자의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-146">[in] The domain name of the user.</span></span> <span data-ttu-id="f0c67-147">자세한 내용은 [Connectserverwmi](connectserverwmi.md) 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c67-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="f0c67-148">반환 값</span><span class="sxs-lookup"><span data-stu-id="f0c67-148">Return value</span></span>

<span data-ttu-id="f0c67-149">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f0c67-150">상수</span><span class="sxs-lookup"><span data-stu-id="f0c67-150">Constant</span></span>  |<span data-ttu-id="f0c67-151">값</span><span class="sxs-lookup"><span data-stu-id="f0c67-151">Value</span></span>  |<span data-ttu-id="f0c67-152">설명</span><span class="sxs-lookup"><span data-stu-id="f0c67-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="f0c67-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="f0c67-153">0x80041003</span></span> | <span data-ttu-id="f0c67-154">사용자에 게 함수가 반환할 수 있는 하나 이상의 클래스를 볼 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="f0c67-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f0c67-155">0x80041001</span></span> | <span data-ttu-id="f0c67-156">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f0c67-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f0c67-157">0x80041008</span></span> | <span data-ttu-id="f0c67-158">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="f0c67-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="f0c67-159">0x80041017</span></span> | <span data-ttu-id="f0c67-160">쿼리에 구문 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="f0c67-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="f0c67-161">0x80041018</span></span> | <span data-ttu-id="f0c67-162">요청한 쿼리 언어는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="f0c67-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="f0c67-163">0x8004106c</span></span> | <span data-ttu-id="f0c67-164">쿼리가 너무 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f0c67-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f0c67-165">0x80041006</span></span> | <span data-ttu-id="f0c67-166">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="f0c67-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="f0c67-167">0x80041033</span></span> | <span data-ttu-id="f0c67-168">WMI가 중지 되었다가 다시 시작 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="f0c67-169">[Connectserverwmi](connectserverwmi.md) 를 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="f0c67-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="f0c67-170">0x80041015</span></span> | <span data-ttu-id="f0c67-171">현재 프로세스와 WMI 간의 RPC (원격 프로시저 호출) 링크에 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="f0c67-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f0c67-172">0x80041002</span></span> | <span data-ttu-id="f0c67-173">쿼리에서 존재 하지 않는 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f0c67-174">0</span><span class="sxs-lookup"><span data-stu-id="f0c67-174">0</span></span> | <span data-ttu-id="f0c67-175">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="f0c67-176">주의</span><span class="sxs-lookup"><span data-stu-id="f0c67-176">Remarks</span></span>

<span data-ttu-id="f0c67-177">이 함수는 [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="f0c67-178">이 함수는 `strQuery` 매개 변수에 지정 된 쿼리를 처리 하 고 호출자가 쿼리 결과에 액세스할 수 있는 열거자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="f0c67-179">열거자는 [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) 인터페이스에 대 한 포인터입니다. 쿼리 결과는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인터페이스를 통해 사용할 수 있는 클래스 개체의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="f0c67-180">WQL 쿼리에서 사용할 수 있는 `AND` 및 `OR` 키워드 수에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="f0c67-181">복잡 한 쿼리에 사용 되는 WQL 키워드가 많은 경우 WMI가 `WBEM_E_QUOTA_VIOLATION` (또는 0x8004106c) 오류 코드를 `HRESULT` 값으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="f0c67-182">WQL 키워드의 제한은 쿼리의 복잡 한 정도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="f0c67-183">함수 호출이 실패 하면 [Geterrorinfo](geterrorinfo.md) 함수를 호출 하 여 추가 오류 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c67-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0c67-184">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0c67-184">Requirements</span></span>

<span data-ttu-id="f0c67-185">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c67-185">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f0c67-186">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="f0c67-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="f0c67-187">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c67-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f0c67-188">참조</span><span class="sxs-lookup"><span data-stu-id="f0c67-188">See also</span></span>

- [<span data-ttu-id="f0c67-189">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="f0c67-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
