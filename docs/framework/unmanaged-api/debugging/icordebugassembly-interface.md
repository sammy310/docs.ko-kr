---
description: '자세히 알아보기: ICorDebugAssembly 인터페이스'
title: ICorDebugAssembly 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: 746b5f4b2f26550788708d93bf0dd50f5f495041
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711949"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="8e855-103">ICorDebugAssembly 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e855-103">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="8e855-104">어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e855-104">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e855-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8e855-105">Methods</span></span>  
  
|<span data-ttu-id="8e855-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8e855-106">Method</span></span>|<span data-ttu-id="8e855-107">설명</span><span class="sxs-lookup"><span data-stu-id="8e855-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e855-108">EnumerateModules 메서드</span><span class="sxs-lookup"><span data-stu-id="8e855-108">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="8e855-109">어셈블리에 포함 된 모듈의 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e855-109">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="8e855-110">GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="8e855-110">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="8e855-111">이 인스턴스를 포함 하는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugAssembly` .</span><span class="sxs-lookup"><span data-stu-id="8e855-111">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="8e855-112">GetCodeBase 메서드</span><span class="sxs-lookup"><span data-stu-id="8e855-112">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="8e855-113">현재 버전의 .NET Framework에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8e855-113">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="8e855-114">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="8e855-114">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="8e855-115">어셈블리의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e855-115">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="8e855-116">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="8e855-116">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="8e855-117">어셈블리가 실행 되는 ICorDebugProcess 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e855-117">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e855-118">설명</span><span class="sxs-lookup"><span data-stu-id="8e855-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e855-119">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e855-119">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e855-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e855-120">Requirements</span></span>  

 <span data-ttu-id="8e855-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e855-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e855-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e855-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e855-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e855-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e855-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e855-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e855-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e855-125">See also</span></span>

- [<span data-ttu-id="8e855-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e855-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
