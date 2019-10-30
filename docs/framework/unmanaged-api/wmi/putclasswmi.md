---
title: PutClassWmi 함수 (관리 되지 않는 API 참조)
description: PutClassWmi 함수는 새 클래스를 만들거나 기존 클래스를 업데이트 합니다.
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
ms.openlocfilehash: 95a5e1f6339bde9dfe5c5ad9f989fc06e10fa7f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101787"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="fb4e0-103">PutClassWmi 함수</span><span class="sxs-lookup"><span data-stu-id="fb4e0-103">PutClassWmi function</span></span>

<span data-ttu-id="fb4e0-104">새 클래스를 만들거나 기존 클래스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fb4e0-105">구문</span><span class="sxs-lookup"><span data-stu-id="fb4e0-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="fb4e0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb4e0-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="fb4e0-107">진행 유효한 클래스 정의에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="fb4e0-108">필요한 모든 속성 값을 사용 하 여 올바르게 초기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="fb4e0-109">진행 이 함수의 동작에 영향을 주는 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="fb4e0-110">다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fb4e0-111">상수</span><span class="sxs-lookup"><span data-stu-id="fb4e0-111">Constant</span></span>  |<span data-ttu-id="fb4e0-112">값</span><span class="sxs-lookup"><span data-stu-id="fb4e0-112">Value</span></span>  |<span data-ttu-id="fb4e0-113">설명</span><span class="sxs-lookup"><span data-stu-id="fb4e0-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="fb4e0-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="fb4e0-114">0x20000</span></span> | <span data-ttu-id="fb4e0-115">설정 되 면 WMI는 수정 된 버전의 한정자를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="fb4e0-116">설정 되지 않은 경우에는이 개체가 지역화 되지 않는다고 가정 하 고 모든 한정자가이 인스턴스와 함께 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="fb4e0-117">0</span><span class="sxs-lookup"><span data-stu-id="fb4e0-117">0</span></span> | <span data-ttu-id="fb4e0-118">존재 하지 않는 경우 클래스를 만들거나 이미 있는 경우 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="fb4e0-119">1</span><span class="sxs-lookup"><span data-stu-id="fb4e0-119">1</span></span> | <span data-ttu-id="fb4e0-120">클래스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-120">Update the class.</span></span> <span data-ttu-id="fb4e0-121">호출이 성공 하려면 클래스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="fb4e0-122">2</span><span class="sxs-lookup"><span data-stu-id="fb4e0-122">2</span></span> | <span data-ttu-id="fb4e0-123">클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-123">Create the class.</span></span> <span data-ttu-id="fb4e0-124">클래스가 이미 있으면 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="fb4e0-125">0x10</span><span class="sxs-lookup"><span data-stu-id="fb4e0-125">0x10</span></span> | <span data-ttu-id="fb4e0-126">플래그는 동기 호출을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="fb4e0-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="fb4e0-127">0x10000</span></span> | <span data-ttu-id="fb4e0-128">이 클래스가 변경 되었음을 나타내기 위해 `PutClassWmi`를 호출할 때 푸시 공급자는이 플래그를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="fb4e0-129">0</span><span class="sxs-lookup"><span data-stu-id="fb4e0-129">0</span></span> | <span data-ttu-id="fb4e0-130">파생 클래스가 없고 해당 클래스의 인스턴스가 없는 경우 클래스를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="fb4e0-131">또한 설명 한정자와 같이 중요 하지 않은 한정자만 변경 하는 경우 모든 경우에 업데이트를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="fb4e0-132">클래스의 인스턴스 또는 변경 내용이 중요 한 한정자 인 경우 업데이트는 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="fb4e0-133">0x20</span><span class="sxs-lookup"><span data-stu-id="fb4e0-133">0x20</span></span> | <span data-ttu-id="fb4e0-134">변경으로 인해 자식 클래스가 충돌 하지 않는 한 자식 클래스가 있어도 클래스의 업데이트를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="fb4e0-135">예를 들어이 플래그를 사용 하면 자식 클래스에서 이전에 언급 되지 않은 기본 클래스에 새 속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="fb4e0-136">클래스에 인스턴스가 있으면 업데이트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="fb4e0-137">0x40</span><span class="sxs-lookup"><span data-stu-id="fb4e0-137">0x40</span></span> | <span data-ttu-id="fb4e0-138">충돌 하는 자식 클래스가 있을 때 클래스를 강제로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="fb4e0-139">예를 들어,이 플래그는 클래스 한정자가 자식 클래스에 정의 되어 있고 기본 클래스가 기존 클래스와 충돌 하는 동일한 한정자를 추가 하려고 하는 경우 업데이트를 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="fb4e0-140">Force 모드에서 tis 충돌은 자식 클래스에서 충돌 하는 한정자를 삭제 하 여 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="fb4e0-141">진행 일반적으로이 값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="fb4e0-142">그렇지 않으면 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 [iwbemcontext 개체가 올바르지](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="fb4e0-143">제한이 `null`경우이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="fb4e0-144">`lFlags`에 `WBEM_FLAG_RETURN_IMMEDIATELY`포함 되어 있으면 함수가 `WBEM_S_NO_ERROR`를 사용 하 여 즉시 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="fb4e0-145">`ppCallResult` 매개 변수는 새 [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) 개체에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="fb4e0-146">반환 값</span><span class="sxs-lookup"><span data-stu-id="fb4e0-146">Return value</span></span>

<span data-ttu-id="fb4e0-147">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fb4e0-148">상수</span><span class="sxs-lookup"><span data-stu-id="fb4e0-148">Constant</span></span>  |<span data-ttu-id="fb4e0-149">값</span><span class="sxs-lookup"><span data-stu-id="fb4e0-149">Value</span></span>  |<span data-ttu-id="fb4e0-150">설명</span><span class="sxs-lookup"><span data-stu-id="fb4e0-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="fb4e0-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="fb4e0-151">0x80041003</span></span> | <span data-ttu-id="fb4e0-152">사용자에 게 클래스를 만들거나 수정할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="fb4e0-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="fb4e0-153">0x80041001</span></span> | <span data-ttu-id="fb4e0-154">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="fb4e0-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="fb4e0-155">0x80041010</span></span> | <span data-ttu-id="fb4e0-156">지정 된 클래스가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-156">The specified class is not valid.</span></span> <span data-ttu-id="fb4e0-157">일반적으로이는 `pObject` 인스턴스 개체를 지정 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fb4e0-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fb4e0-158">0x80041008</span></span> | <span data-ttu-id="fb4e0-159">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="fb4e0-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="fb4e0-160">0x80041016</span></span> | <span data-ttu-id="fb4e0-161">지정한 클래스 이름이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="fb4e0-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="fb4e0-162">0x80041025</span></span> | <span data-ttu-id="fb4e0-163">하위 클래스를 무효화 하는 변경 작업을 수행 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="fb4e0-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="fb4e0-164">0x80041019</span></span> | <span data-ttu-id="fb4e0-165">`WBEM_FLAG_CREATE_ONLY` 플래그가 지정 되었지만 클래스가 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="fb4e0-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="fb4e0-166">0x80041002</span></span> | <span data-ttu-id="fb4e0-167">`lFlags`에서 `WBEM_FLAG_UPDATE_ONLY` 지정 되었으며 클래스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="fb4e0-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="fb4e0-168">0x80041020</span></span> | <span data-ttu-id="fb4e0-169">클래스에 필요한 속성이 모두 설정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fb4e0-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fb4e0-170">0x80041006</span></span> | <span data-ttu-id="fb4e0-171">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="fb4e0-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="fb4e0-172">0x80041033</span></span> | <span data-ttu-id="fb4e0-173">WMI가 중지 되었다가 다시 시작 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="fb4e0-174">[Connectserverwmi](connectserverwmi.md) 를 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="fb4e0-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="fb4e0-175">0x80041015</span></span> | <span data-ttu-id="fb4e0-176">현재 프로세스와 WMI 간의 RPC (원격 프로시저 호출) 링크에 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="fb4e0-177">0</span><span class="sxs-lookup"><span data-stu-id="fb4e0-177">0</span></span> | <span data-ttu-id="fb4e0-178">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="fb4e0-179">주의</span><span class="sxs-lookup"><span data-stu-id="fb4e0-179">Remarks</span></span>

<span data-ttu-id="fb4e0-180">이 함수는 [IWbemServices::P utClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="fb4e0-181">사용자는 이름이 밑줄로 시작 하거나 끝나는 클래스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="fb4e0-182">함수 호출이 실패 하면 [Geterrorinfo](geterrorinfo.md) 함수를 호출 하 여 추가 오류 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb4e0-183">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb4e0-183">Requirements</span></span>

<span data-ttu-id="fb4e0-184">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb4e0-184">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="fb4e0-185">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="fb4e0-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="fb4e0-186">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fb4e0-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fb4e0-187">참조</span><span class="sxs-lookup"><span data-stu-id="fb4e0-187">See also</span></span>

- [<span data-ttu-id="fb4e0-188">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="fb4e0-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
