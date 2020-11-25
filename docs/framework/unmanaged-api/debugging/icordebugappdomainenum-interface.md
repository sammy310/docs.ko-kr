---
title: ICorDebugAppDomainEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 37b6bcb48681704e3db47f81a51a9d21f00dfb37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723196"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="e1a94-102">ICorDebugAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1a94-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="e1a94-103">`Next` `ICorDebugAppDomainEnum` 열거형의 다음 위치에서 시작 하 여 지정 된 수의 값을 반환 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a94-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="e1a94-104">이 인터페이스는 "ICorDebugEnum"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a94-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1a94-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e1a94-105">Methods</span></span>  
  
|<span data-ttu-id="e1a94-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e1a94-106">Method</span></span>|<span data-ttu-id="e1a94-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1a94-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1a94-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="e1a94-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="e1a94-109">현재 커서 위치에서 시작 하 여 컬렉션에서 지정 된 수의 응용 프로그램 도메인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1a94-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1a94-110">설명</span><span class="sxs-lookup"><span data-stu-id="e1a94-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1a94-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a94-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1a94-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1a94-112">Requirements</span></span>  

 <span data-ttu-id="e1a94-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1a94-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a94-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1a94-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1a94-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1a94-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1a94-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a94-117">참조</span><span class="sxs-lookup"><span data-stu-id="e1a94-117">See also</span></span>

- [<span data-ttu-id="e1a94-118">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1a94-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="e1a94-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1a94-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
