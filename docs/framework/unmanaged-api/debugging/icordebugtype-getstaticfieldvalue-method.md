---
title: ICorDebugType::GetStaticFieldValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c6b86c5ce3cc246af600d9b65d2fe12a0427f9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663845"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="407b7-102">ICorDebugType::GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="407b7-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="407b7-103">지정한 스택 프레임이 토큰 지정 된 필드에서 참조 하는 정적 필드의 값이 포함 된 ICorDebugValue 개체 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="407b7-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="407b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="407b7-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="407b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="407b7-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="407b7-106">[in] `mdFieldDef` 정적 필드를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="407b7-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="407b7-107">[in] 스택 프레임을 나타내는 ICorDebugFrame 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="407b7-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="407b7-108">[out] 주소에 대 한 포인터는 `ICorDebugValue` 정적 필드의 값이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="407b7-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="407b7-109">설명</span><span class="sxs-lookup"><span data-stu-id="407b7-109">Remarks</span></span>  
 <span data-ttu-id="407b7-110">합니다 `GetStaticFieldValue` 메서드에 사용할 수 형식이 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE, 경우에 표시 된 대로 합니다 [icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="407b7-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="407b7-111">제네릭이 아닌 형식에 대 한 작업을 수행 하 여 `GetStaticFieldValue` 호출과 동일 [icordebugclass:: Getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) 반환한 ICorDebugClass 개체에서 [icordebugtype:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="407b7-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="407b7-112">제네릭 형식의 정적 필드 값을 특정 인스턴스화를 상대적으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="407b7-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="407b7-113">또한 정적 필드 스레드, 컨텍스트 또는 응용 프로그램 도메인을 기준으로 될 수, 하는 경우 다음 스택 프레임 데 도움이 됩니다 적절 한 값을 결정 하는 디버거.</span><span class="sxs-lookup"><span data-stu-id="407b7-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="407b7-114">설명</span><span class="sxs-lookup"><span data-stu-id="407b7-114">Remarks</span></span>  
 <span data-ttu-id="407b7-115">`GetStaticFieldValue` 호출할 때에 사용할 수 있습니다 `ICorDebugType::GetType` ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="407b7-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="407b7-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="407b7-116">Requirements</span></span>  
 <span data-ttu-id="407b7-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="407b7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="407b7-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="407b7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="407b7-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="407b7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="407b7-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="407b7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
