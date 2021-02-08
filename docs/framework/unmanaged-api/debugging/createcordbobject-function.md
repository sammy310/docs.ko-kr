---
description: '자세히 알아보기: CreateCordbObject 함수'
title: CreateCordbObject 함수
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: b6a585fc89f780b22f842127e1923414dbb8230f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801477"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="ed6c9-103">CreateCordbObject 함수</span><span class="sxs-lookup"><span data-stu-id="ed6c9-103">CreateCordbObject Function</span></span>

<span data-ttu-id="ed6c9-104">원격 프로세스에서 관리 되는 디버깅 세션을 인스턴스화하기 위한 기능을 제공 하는 디버거 인터페이스 ([ICorDebug](icordebug-interface.md))를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-104">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed6c9-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed6c9-105">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed6c9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed6c9-106">Parameters</span></span>  

 `iDebuggerVersion`  
 <span data-ttu-id="ed6c9-107">[in] 대상 프로세스의 디버거 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-107">[in] Debugger version of the target process.</span></span> <span data-ttu-id="ed6c9-108">원격 디버깅의 경우 이 매개 변수는 CorDebugVersion_2_0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-108">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="ed6c9-109">제한이 [ICorDebug](icordebug-interface.md) 인터페이스로 캐스팅 되 고 반환 되는 개체에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-109">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed6c9-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="ed6c9-110">Return Value</span></span>  

 <span data-ttu-id="ed6c9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed6c9-111">S_OK</span></span>  
 <span data-ttu-id="ed6c9-112">프로세스의 CLR 수가 성공적으로 확인되었으며 해당 핸들 및 경로 배열이 제대로 채워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-112">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="ed6c9-113">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ed6c9-113">E_INVALIDARG</span></span>  
 <span data-ttu-id="ed6c9-114">`ppCordb`가 null이거나 `iDebuggerVersion`이 CorDebugVersion_2_0이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-114">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="ed6c9-115">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ed6c9-115">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="ed6c9-116">`ppCordb`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-116">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="ed6c9-117">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="ed6c9-117">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ed6c9-118">기타 실패</span><span class="sxs-lookup"><span data-stu-id="ed6c9-118">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed6c9-119">설명</span><span class="sxs-lookup"><span data-stu-id="ed6c9-119">Remarks</span></span>  

 <span data-ttu-id="ed6c9-120">에서 반환 되는 [ICorDebug](icordebug-interface.md) 인터페이스는 `ppCordb` 모든 관리 되는 디버깅 서비스에 대 한 최상위 수준 디버깅 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-120">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed6c9-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed6c9-121">Requirements</span></span>  

 <span data-ttu-id="ed6c9-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed6c9-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed6c9-123">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="ed6c9-123">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ed6c9-124">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ed6c9-124">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ed6c9-125">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ed6c9-125">**.NET Framework Versions:** 3.5 SP1</span></span>
