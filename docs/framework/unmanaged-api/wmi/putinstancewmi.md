---
title: PutInstanceWmi 함수 (관리 되지 않는 API 참조)
description: PutInstanceWmi 함수를 만들거나 기존 클래스의 인스턴스를 업데이트 합니다.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19f657fd76f73c4016824511079e6f037bc3bc53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597338"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="039e2-103">PutInstanceWmi 함수</span><span class="sxs-lookup"><span data-stu-id="039e2-103">PutInstanceWmi function</span></span>

<span data-ttu-id="039e2-104">기존 클래스의 인스턴스를 만들거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="039e2-105">인스턴스가 WMI 리포지토리에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="039e2-106">구문</span><span class="sxs-lookup"><span data-stu-id="039e2-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="039e2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="039e2-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="039e2-108">[in] 쓸 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="039e2-109">[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="039e2-110">에 정의 된 다음 값을 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="039e2-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="039e2-111">상수</span><span class="sxs-lookup"><span data-stu-id="039e2-111">Constant</span></span>  |<span data-ttu-id="039e2-112">값</span><span class="sxs-lookup"><span data-stu-id="039e2-112">Value</span></span>  |<span data-ttu-id="039e2-113">설명</span><span class="sxs-lookup"><span data-stu-id="039e2-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="039e2-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="039e2-114">0x20000</span></span> | <span data-ttu-id="039e2-115">경우 설정, WMI 저장 하지 않습니다 사용 하 여 모든 한정자를 **Amended** 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="039e2-116">그렇지 않은 경우 집합 가정는이 개체에 지역화 되지 않으면 모든 한정자는이 인스턴스를 사용 하 여 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="039e2-117">0</span><span class="sxs-lookup"><span data-stu-id="039e2-117">0</span></span> | <span data-ttu-id="039e2-118">존재 하거나 이미 있으면 덮어 쓸까요 하지 않는 경우 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="039e2-119">1</span><span class="sxs-lookup"><span data-stu-id="039e2-119">1</span></span> | <span data-ttu-id="039e2-120">인스턴스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-120">Update the instance.</span></span> <span data-ttu-id="039e2-121">인스턴스 수에 대 한 호출에 대 한 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="039e2-122">2</span><span class="sxs-lookup"><span data-stu-id="039e2-122">2</span></span> | <span data-ttu-id="039e2-123">인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-123">Create the instance.</span></span> <span data-ttu-id="039e2-124">인스턴스가 이미 있는 경우 호출은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="039e2-125">0x10</span><span class="sxs-lookup"><span data-stu-id="039e2-125">0x10</span></span> | <span data-ttu-id="039e2-126">플래그를 사용 하면 일부 동기 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="039e2-127">[in] 이 값은 일반적으로 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="039e2-128">그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="039e2-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="039e2-129">[out] 경우 `null`,이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="039e2-130">하는 경우 `lFlags` 포함 `WBEM_FLAG_RETURN_IMMEDIATELY`, 함수에서 사용 하 여 즉시 반환 `WBEM_S_NO_ERROR`합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="039e2-131">합니다 `ppCallResult` 매개 변수는 새 포인터를 받습니다 [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="039e2-132">반환 값</span><span class="sxs-lookup"><span data-stu-id="039e2-132">Return value</span></span>

<span data-ttu-id="039e2-133">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="039e2-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="039e2-134">상수</span><span class="sxs-lookup"><span data-stu-id="039e2-134">Constant</span></span>  |<span data-ttu-id="039e2-135">값</span><span class="sxs-lookup"><span data-stu-id="039e2-135">Value</span></span>  |<span data-ttu-id="039e2-136">설명</span><span class="sxs-lookup"><span data-stu-id="039e2-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="039e2-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="039e2-137">0x80041003</span></span> | <span data-ttu-id="039e2-138">사용자 지정된 된 클래스의 인스턴스를 업데이트할 수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="039e2-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="039e2-139">0x80041001</span></span> | <span data-ttu-id="039e2-140">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="039e2-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="039e2-141">0x80041010</span></span> | <span data-ttu-id="039e2-142">이 인스턴스를 지 원하는 클래스가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="039e2-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="039e2-143">0x80041028</span></span> | <span data-ttu-id="039e2-144">`null` 될 수 없는 속성에 대해 지정 된 `null`로 표시 되는 것과 같은 **인덱싱됨** 또는 **Not_Null** 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="039e2-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="039e2-145">0x8004100f</span></span> | <span data-ttu-id="039e2-146">지정 된 인스턴스가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-146">The specified instance is not valid.</span></span> <span data-ttu-id="039e2-147">(예를 들어 호출 `PutInstanceWmi` 클래스를 사용 하 여이 값을 반환 합니다.)</span><span class="sxs-lookup"><span data-stu-id="039e2-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="039e2-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="039e2-148">0x80041008</span></span> | <span data-ttu-id="039e2-149">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="039e2-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="039e2-150">0x80041019</span></span> | <span data-ttu-id="039e2-151">`WBEM_FLAG_CREATE_ONLY` 플래그 지정 했지만 인스턴스가 이미 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="039e2-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="039e2-152">0x80041002</span></span> | <span data-ttu-id="039e2-153">`WBEM_FLAG_UPDATE_ONLY` 에 지정 된 `lFlags`, 하는데 인스턴스에 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="039e2-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="039e2-154">0x80041006</span></span> | <span data-ttu-id="039e2-155">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="039e2-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="039e2-156">0x80041033</span></span> | <span data-ttu-id="039e2-157">WMI는 아마도 중지 및 다시 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="039e2-158">호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="039e2-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="039e2-159">0x80041015</span></span> | <span data-ttu-id="039e2-160">현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="039e2-161">0</span><span class="sxs-lookup"><span data-stu-id="039e2-161">0</span></span> | <span data-ttu-id="039e2-162">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="039e2-163">설명</span><span class="sxs-lookup"><span data-stu-id="039e2-163">Remarks</span></span>

<span data-ttu-id="039e2-164">이 함수에 대 한 호출을 래핑하는 [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) 메서드.</span><span class="sxs-lookup"><span data-stu-id="039e2-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="039e2-165">`PutInstanceWmi` 함수 지원 인스턴스를 만들고만 기존 클래스의 인스턴스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="039e2-166">방법에 따라 `pCtx` 매개 변수는 설정, 일부 또는 모든 인스턴스의 속성이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="039e2-167">인스턴스의 경우에서 가리키는 `pInst` 호출 책임 서브 클래스 파생 되는 클래스에 대 한 모든 공급자 Windows 관리 하위 클래스에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="039e2-168">이러한 공급자의 모든 원본에 대 한 필수 `PutInstanceWmi` 요청이 성공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="039e2-169">계층의 최상위 클래스를 지 원하는 공급자는 먼저 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="039e2-170">호출 순서 맨 위에 클래스의 서브 클래스를 사용 하 여 계속 하 고 Windows 관리에서 가리키는 인스턴스를 소유 하는 클래스에 대 한 공급자에 도달할 때까지 위에서 아래로 진행 `pInst`합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="039e2-171">Windows 관리 인스턴스의 자식 클래스에 대 한 공급자를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="039e2-172">응용 프로그램 클래스 계층에 속하는 인스턴스를 업데이트 해야 하는 경우는 `pInst` 매개 변수를 수정할 속성이 포함 된 인스턴스를 가리키도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="039e2-173">즉, 대상 인스턴스에 속하는 것이 좋습니다 **ClassB**합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="039e2-174">합니다 **ClassB** 에서 파생 되는 인스턴스 **ClassA**, 및 **ClassA** 속성을 정의 합니다 **PropA**합니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="039e2-175">응용 프로그램의 값을 변경 하려는 경우 **PropA** 에 **ClassB** 설정 해야 인스턴스 `pInst` 인스턴스의 보다는 해당 인스턴스 **ClassA** .</span><span class="sxs-lookup"><span data-stu-id="039e2-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="039e2-176">호출 `PutInstanceWmi` 추상 클래스의 인스턴스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="039e2-177">함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="039e2-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="039e2-178">요구 사항</span><span class="sxs-lookup"><span data-stu-id="039e2-178">Requirements</span></span>

<span data-ttu-id="039e2-179">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="039e2-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="039e2-180">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="039e2-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="039e2-181">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="039e2-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="039e2-182">참고자료</span><span class="sxs-lookup"><span data-stu-id="039e2-182">See also</span></span>

- [<span data-ttu-id="039e2-183">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="039e2-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)