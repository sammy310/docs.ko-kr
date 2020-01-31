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
ms.openlocfilehash: 8160bb5b9ca5e0a4e22a1a831e978eaf125e7605
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870494"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="d15d1-102">ICorProfilerInfo::GetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="d15d1-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="d15d1-103">MSIL (Microsoft 중간 언어) 코드에서 헤더를 시작 하는 메서드의 본문에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d15d1-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d15d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="d15d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d15d1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d15d1-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d15d1-106">진행 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d15d1-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="d15d1-107">진행 메서드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d15d1-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="d15d1-108">제한이 메서드의 헤더에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d15d1-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="d15d1-109">[out] 메서드의 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d15d1-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d15d1-110">주의</span><span class="sxs-lookup"><span data-stu-id="d15d1-110">Remarks</span></span>  
 <span data-ttu-id="d15d1-111">메서드는 해당 메서드가 상주 하는 모듈로 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d15d1-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="d15d1-112">`GetILFunctionBody` 메서드는 CLR (공용 언어 런타임)에 의해 로드 되기 전에 도구에 MSIL 코드에 대 한 액세스를 제공 하도록 설계 되었기 때문에 메서드의 메타 데이터 토큰을 사용 하 여 원하는 인스턴스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d15d1-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="d15d1-113">`methodId`가 MSIL 코드 (예: 추상 메서드 또는 플랫폼 호출 (PInvoke) 메서드)를 사용 하지 않고 메서드를 가리키는 경우에는 CORPROF_E_FUNCTION_NOT_IL HRESULT를 반환할 수 `GetILFunctionBody`.</span><span class="sxs-lookup"><span data-stu-id="d15d1-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d15d1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d15d1-114">Requirements</span></span>  
 <span data-ttu-id="d15d1-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d15d1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d15d1-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d15d1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d15d1-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d15d1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d15d1-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d15d1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15d1-119">참조</span><span class="sxs-lookup"><span data-stu-id="d15d1-119">See also</span></span>

- [<span data-ttu-id="d15d1-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d15d1-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
