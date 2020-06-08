---
title: ICorProfilerInfo::GetClassFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 12b4b897f9dc51175037d39c0368b6ce59fefefb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498481"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="d4bb7-102">ICorProfilerInfo::GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d4bb7-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="d4bb7-103">메타 데이터 토큰이 지정 된 경우 클래스의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4bb7-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="d4bb7-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4bb7-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d4bb7-105">대신 [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4bb7-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4bb7-106">구문</span><span class="sxs-lookup"><span data-stu-id="d4bb7-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4bb7-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4bb7-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="d4bb7-108">진행 클래스가 포함 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d4bb7-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="d4bb7-109">진행 `mdTypeDef`클래스를 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d4bb7-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="d4bb7-110">제한이 클래스 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4bb7-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4bb7-111">설명</span><span class="sxs-lookup"><span data-stu-id="d4bb7-111">Remarks</span></span>  
 <span data-ttu-id="d4bb7-112">이 메서드는 사용 되지 않습니다. 대신 `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` 모든 형식에 대해를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4bb7-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4bb7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4bb7-113">Requirements</span></span>  
 <span data-ttu-id="d4bb7-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4bb7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4bb7-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d4bb7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d4bb7-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4bb7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4bb7-117">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d4bb7-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4bb7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4bb7-118">See also</span></span>

- [<span data-ttu-id="d4bb7-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4bb7-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
