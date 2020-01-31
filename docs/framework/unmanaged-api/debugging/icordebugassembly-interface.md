---
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
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784668"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="77fd7-102">ICorDebugAssembly 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77fd7-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="77fd7-103">어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77fd7-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77fd7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="77fd7-104">Methods</span></span>  
  
|<span data-ttu-id="77fd7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="77fd7-105">Method</span></span>|<span data-ttu-id="77fd7-106">설명</span><span class="sxs-lookup"><span data-stu-id="77fd7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77fd7-107">EnumerateModules 메서드</span><span class="sxs-lookup"><span data-stu-id="77fd7-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="77fd7-108">어셈블리에 포함 된 모듈의 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77fd7-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="77fd7-109">GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="77fd7-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="77fd7-110">이 `ICorDebugAssembly` 인스턴스를 포함 하는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77fd7-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="77fd7-111">GetCodeBase 메서드</span><span class="sxs-lookup"><span data-stu-id="77fd7-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="77fd7-112">현재 버전의 .NET Framework에서 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="77fd7-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="77fd7-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="77fd7-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="77fd7-114">어셈블리의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77fd7-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="77fd7-115">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="77fd7-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="77fd7-116">어셈블리가 실행 되는 ICorDebugProcess 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77fd7-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77fd7-117">주의</span><span class="sxs-lookup"><span data-stu-id="77fd7-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77fd7-118">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77fd7-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77fd7-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77fd7-119">Requirements</span></span>  
 <span data-ttu-id="77fd7-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77fd7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77fd7-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77fd7-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77fd7-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77fd7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77fd7-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77fd7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77fd7-124">참조</span><span class="sxs-lookup"><span data-stu-id="77fd7-124">See also</span></span>

- [<span data-ttu-id="77fd7-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77fd7-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
