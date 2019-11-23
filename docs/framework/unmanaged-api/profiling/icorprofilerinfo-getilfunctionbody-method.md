---
title: ICorProfilerInfo::GetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
ms.openlocfilehash: a7ec50c91ce02958d0d44643d4f79da1680532aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450364"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="d41cc-102">ICorProfilerInfo::GetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="d41cc-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="d41cc-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span><span class="sxs-lookup"><span data-stu-id="d41cc-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d41cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="d41cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d41cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d41cc-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d41cc-106">[in] The ID of the module in which the function resides.</span><span class="sxs-lookup"><span data-stu-id="d41cc-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="d41cc-107">[in] The metadata token for the method.</span><span class="sxs-lookup"><span data-stu-id="d41cc-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="d41cc-108">[out] A pointer to the method's header.</span><span class="sxs-lookup"><span data-stu-id="d41cc-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="d41cc-109">[out] An integer that specifies the size of the method.</span><span class="sxs-lookup"><span data-stu-id="d41cc-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d41cc-110">주의</span><span class="sxs-lookup"><span data-stu-id="d41cc-110">Remarks</span></span>  
 <span data-ttu-id="d41cc-111">A method is scoped by the module in which it lives.</span><span class="sxs-lookup"><span data-stu-id="d41cc-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="d41cc-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span><span class="sxs-lookup"><span data-stu-id="d41cc-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="d41cc-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span><span class="sxs-lookup"><span data-stu-id="d41cc-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d41cc-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d41cc-114">Requirements</span></span>  
 <span data-ttu-id="d41cc-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d41cc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d41cc-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d41cc-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d41cc-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d41cc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d41cc-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d41cc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41cc-119">참조</span><span class="sxs-lookup"><span data-stu-id="d41cc-119">See also</span></span>

- [<span data-ttu-id="d41cc-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d41cc-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
