---
title: ICoreClrDebugTarget::EnumProcesses 메서드
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
ms.openlocfilehash: 0c1b18f24fd30b5f6d5e85633fc0c25839aba6df
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396418"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="85549-102">ICoreClrDebugTarget::EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="85549-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="85549-103">원격 컴퓨터에서 실행 중인 프로세스를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="85549-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85549-104">구문</span><span class="sxs-lookup"><span data-stu-id="85549-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85549-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85549-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="85549-106">[out] `ppProcs`에 반환된 프로세스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="85549-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="85549-107">이 값은 0일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85549-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="85549-108">제한이 원격 컴퓨터에서 실행 중인 프로세스를 나타내는 [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="85549-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85549-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="85549-109">Return Value</span></span>  
 <span data-ttu-id="85549-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="85549-110">S_OK</span></span>  
 <span data-ttu-id="85549-111">성공.</span><span class="sxs-lookup"><span data-stu-id="85549-111">Success.</span></span>  
  
 <span data-ttu-id="85549-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="85549-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="85549-113">`ppProcs`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85549-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="85549-114">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="85549-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="85549-115">기타 실패</span><span class="sxs-lookup"><span data-stu-id="85549-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85549-116">설명</span><span class="sxs-lookup"><span data-stu-id="85549-116">Remarks</span></span>  
 <span data-ttu-id="85549-117">이 메서드에 의해 할당 된 메모리를 해제 하려면 [ICoreClrDebugTarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="85549-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85549-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85549-118">Requirements</span></span>  
 <span data-ttu-id="85549-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85549-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85549-120">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="85549-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="85549-121">**라이브러리:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="85549-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="85549-122">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="85549-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85549-123">참조</span><span class="sxs-lookup"><span data-stu-id="85549-123">See also</span></span>

- [<span data-ttu-id="85549-124">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85549-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
