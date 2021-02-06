---
description: '자세히 알아보기: ICorProfilerInfo:: GetILFunctionBody 메서드'
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
ms.openlocfilehash: 7294592d1a2747dc10f44d1206561a9a1662ce7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647481"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="d2dc0-103">ICorProfilerInfo::GetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="d2dc0-103">ICorProfilerInfo::GetILFunctionBody Method</span></span>

<span data-ttu-id="d2dc0-104">MSIL (Microsoft 중간 언어) 코드에서 헤더를 시작 하는 메서드의 본문에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-104">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2dc0-105">구문</span><span class="sxs-lookup"><span data-stu-id="d2dc0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2dc0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2dc0-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="d2dc0-107">진행 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-107">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="d2dc0-108">진행 메서드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-108">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="d2dc0-109">제한이 메서드의 헤더에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-109">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="d2dc0-110">제한이 메서드의 크기를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-110">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2dc0-111">설명</span><span class="sxs-lookup"><span data-stu-id="d2dc0-111">Remarks</span></span>  

 <span data-ttu-id="d2dc0-112">메서드는 해당 메서드가 상주 하는 모듈로 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-112">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="d2dc0-113">메서드는 `GetILFunctionBody` CLR (공용 언어 런타임)에 의해 로드 되기 전에 도구에 MSIL 코드에 대 한 액세스를 제공 하도록 설계 되었으므로 메서드의 메타 데이터 토큰을 사용 하 여 원하는 인스턴스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-113">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="d2dc0-114">`GetILFunctionBody` 는가 `methodId` MSIL 코드 (예: 추상 메서드 또는 플랫폼 호출 (PInvoke) 메서드)를 사용 하지 않고 메서드를 가리키는 경우 CORPROF_E_FUNCTION_NOT_IL HRESULT를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-114">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2dc0-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2dc0-115">Requirements</span></span>  

 <span data-ttu-id="d2dc0-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2dc0-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2dc0-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2dc0-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2dc0-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2dc0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2dc0-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2dc0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2dc0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2dc0-120">See also</span></span>

- [<span data-ttu-id="d2dc0-121">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2dc0-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
