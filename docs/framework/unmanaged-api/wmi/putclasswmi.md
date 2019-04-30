---
title: PutClassWmi 함수 (관리 되지 않는 API 참조)
description: PutClassWmi 함수 새 클래스를 만들거나 기존 계정을 업데이트 합니다.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9d537f7713233d363f7d408b1cef0485d99d981
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000170"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="63347-103">PutClassWmi 함수</span><span class="sxs-lookup"><span data-stu-id="63347-103">PutClassWmi function</span></span>

<span data-ttu-id="63347-104">새 클래스를 만들거나 기존 클래스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="63347-105">구문</span><span class="sxs-lookup"><span data-stu-id="63347-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="63347-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63347-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="63347-107">[in] 올바른 클래스 정의에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="63347-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="63347-108">모든 필수 속성 값을 사용 하 여 올바르게 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="63347-109">[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="63347-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="63347-110">에 정의 된 다음 값을 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="63347-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="63347-111">상수</span><span class="sxs-lookup"><span data-stu-id="63347-111">Constant</span></span>  |<span data-ttu-id="63347-112">값</span><span class="sxs-lookup"><span data-stu-id="63347-112">Value</span></span>  |<span data-ttu-id="63347-113">설명</span><span class="sxs-lookup"><span data-stu-id="63347-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="63347-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="63347-114">0x20000</span></span> | <span data-ttu-id="63347-115">경우 설정, WMI는 수정 된 버전을 사용 하 여 모든 한정자를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="63347-116">그렇지 않은 경우 집합 가정는이 개체에 지역화 되지 않으면 모든 한정자는이 인스턴스를 사용 하 여 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63347-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="63347-117">0</span><span class="sxs-lookup"><span data-stu-id="63347-117">0</span></span> | <span data-ttu-id="63347-118">존재 하거나 이미 있으면 덮어 쓸까요 하지 않는 경우에 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63347-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="63347-119">1</span><span class="sxs-lookup"><span data-stu-id="63347-119">1</span></span> | <span data-ttu-id="63347-120">클래스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-120">Update the class.</span></span> <span data-ttu-id="63347-121">클래스는 성공에 대 한 호출에 대 한 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="63347-122">2</span><span class="sxs-lookup"><span data-stu-id="63347-122">2</span></span> | <span data-ttu-id="63347-123">클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63347-123">Create the class.</span></span> <span data-ttu-id="63347-124">클래스가 이미 존재 하는 경우 호출은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="63347-125">0x10</span><span class="sxs-lookup"><span data-stu-id="63347-125">0x10</span></span> | <span data-ttu-id="63347-126">플래그를 사용 하면 일부 동기 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="63347-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="63347-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="63347-127">0x10000</span></span> | <span data-ttu-id="63347-128">푸시 공급자를 호출할 때이 플래그를 지정 해야 `PutClassWmi` 나타내려면이 클래스가 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="63347-129">0</span><span class="sxs-lookup"><span data-stu-id="63347-129">0</span></span> | <span data-ttu-id="63347-130">클래스를 없는 파생 된 클래스와 해당 클래스의 인스턴스가 없는 경우 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="63347-131">또한 변경 되는 경우 설명 한정자와 같은 중요 하지 않은 한정자를 모든 경우에 업데이트를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="63347-132">클래스에는 인스턴스 또는 중요 한 한정자는 변경 하는 경우 업데이트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="63347-133">0x20</span><span class="sxs-lookup"><span data-stu-id="63347-133">0x20</span></span> | <span data-ttu-id="63347-134">자식 클래스를 가지으로 자식 클래스를 사용 하 여 변경 충돌이 발생 하지 않습니다 하는 경우에 클래스의 업데이트를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="63347-135">예를 들어,이 플래그는 자식 클래스 중 하나에서 이전에 언급 되지 않은 기본 클래스에 추가 하는 새 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="63347-136">클래스의 인스턴스가 업데이트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="63347-137">0x40</span><span class="sxs-lookup"><span data-stu-id="63347-137">0x40</span></span> | <span data-ttu-id="63347-138">충돌 하는 자식 클래스는 존재할 때 클래스의 업데이트를 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="63347-139">예를 들어,이 플래그는 업데이트 강제 클래스 한정자는 자식 클래스에서 정의 되 고 기본 클래스를 같은 한정자를 추가 하려고 합니다. 기존와 충돌 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="63347-140">강제 모드에서 자식 클래스에 충돌 하는 한정자를 삭제 하 여이 충돌이 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63347-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="63347-141">[in] 이 값은 일반적으로 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="63347-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="63347-142">그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="63347-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="63347-143">[out] 경우 `null`,이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="63347-144">하는 경우 `lFlags` 포함 `WBEM_FLAG_RETURN_IMMEDIATELY`, 함수에서 사용 하 여 즉시 반환 `WBEM_S_NO_ERROR`합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="63347-145">합니다 `ppCallResult` 매개 변수는 새 포인터를 받습니다 [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63347-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="63347-146">반환 값</span><span class="sxs-lookup"><span data-stu-id="63347-146">Return value</span></span>

<span data-ttu-id="63347-147">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="63347-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="63347-148">상수</span><span class="sxs-lookup"><span data-stu-id="63347-148">Constant</span></span>  |<span data-ttu-id="63347-149">값</span><span class="sxs-lookup"><span data-stu-id="63347-149">Value</span></span>  |<span data-ttu-id="63347-150">설명</span><span class="sxs-lookup"><span data-stu-id="63347-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="63347-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="63347-151">0x80041003</span></span> | <span data-ttu-id="63347-152">사용자를 만들거나 클래스를 수정할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="63347-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="63347-153">0x80041001</span></span> | <span data-ttu-id="63347-154">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="63347-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="63347-155">0x80041010</span></span> | <span data-ttu-id="63347-156">지정 된 클래스가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-156">The specified class is not valid.</span></span> <span data-ttu-id="63347-157">일반적으로이 나타내는 `pObject` 인스턴스 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="63347-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="63347-158">0x80041008</span></span> | <span data-ttu-id="63347-159">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="63347-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="63347-160">0x80041016</span></span> | <span data-ttu-id="63347-161">지정 된 클래스 이름이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="63347-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="63347-162">0x80041025</span></span> | <span data-ttu-id="63347-163">서브 클래스를 무효화 하는 변경 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="63347-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="63347-164">0x80041019</span></span> | <span data-ttu-id="63347-165">`WBEM_FLAG_CREATE_ONLY` 플래그를 지정 하지만 클래스가 이미 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="63347-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="63347-166">0x80041002</span></span> | <span data-ttu-id="63347-167">`WBEM_FLAG_UPDATE_ONLY` 에 지정 된 `lFlags`, 클래스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="63347-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="63347-168">0x80041020</span></span> | <span data-ttu-id="63347-169">클래스에 대 한 필수 속성이 모두 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="63347-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="63347-170">0x80041006</span></span> | <span data-ttu-id="63347-171">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="63347-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="63347-172">0x80041033</span></span> | <span data-ttu-id="63347-173">WMI는 아마도 중지 및 다시 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="63347-174">호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="63347-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="63347-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="63347-175">0x80041015</span></span> | <span data-ttu-id="63347-176">현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="63347-177">0</span><span class="sxs-lookup"><span data-stu-id="63347-177">0</span></span> | <span data-ttu-id="63347-178">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="63347-179">설명</span><span class="sxs-lookup"><span data-stu-id="63347-179">Remarks</span></span>

<span data-ttu-id="63347-180">이 함수에 대 한 호출을 래핑하는 [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) 메서드.</span><span class="sxs-lookup"><span data-stu-id="63347-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="63347-181">사용자 이름이 시작 또는 밑줄로 끝나야 하는 클래스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63347-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="63347-182">함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="63347-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="63347-183">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63347-183">Requirements</span></span>

<span data-ttu-id="63347-184">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="63347-184">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="63347-185">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="63347-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="63347-186">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="63347-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="63347-187">참고자료</span><span class="sxs-lookup"><span data-stu-id="63347-187">See also</span></span>

- [<span data-ttu-id="63347-188">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="63347-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)