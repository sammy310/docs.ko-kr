---
title: ICorDebugMDA 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: c4ff28ff1019b5314902a4e71f6d02b5a2fd8d70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710846"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="66fe0-102">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66fe0-102">ICorDebugMDA Interface</span></span>

<span data-ttu-id="66fe0-103">MDA(관리 디버깅 도우미) 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66fe0-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66fe0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="66fe0-104">Methods</span></span>  
  
|<span data-ttu-id="66fe0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="66fe0-105">Method</span></span>|<span data-ttu-id="66fe0-106">설명</span><span class="sxs-lookup"><span data-stu-id="66fe0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66fe0-107">GetDescription 메서드</span><span class="sxs-lookup"><span data-stu-id="66fe0-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="66fe0-108">이 MDA에 대 한 설명을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66fe0-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="66fe0-109">GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="66fe0-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="66fe0-110">이 MDA와 연결 된 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66fe0-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="66fe0-111">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="66fe0-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="66fe0-112">이 MDA의 이름을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66fe0-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="66fe0-113">GetOSThreadId 메서드</span><span class="sxs-lookup"><span data-stu-id="66fe0-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="66fe0-114">이 MDA가 실행 되 고 있는 운영 체제 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66fe0-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="66fe0-115">GetXML 메서드</span><span class="sxs-lookup"><span data-stu-id="66fe0-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="66fe0-116">이 MDA와 연결 된 전체 XML 스트림을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66fe0-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66fe0-117">설명</span><span class="sxs-lookup"><span data-stu-id="66fe0-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66fe0-118">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66fe0-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66fe0-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66fe0-119">Requirements</span></span>  

 <span data-ttu-id="66fe0-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66fe0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66fe0-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66fe0-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66fe0-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66fe0-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66fe0-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66fe0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66fe0-124">참조</span><span class="sxs-lookup"><span data-stu-id="66fe0-124">See also</span></span>

- [<span data-ttu-id="66fe0-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66fe0-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="66fe0-126">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="66fe0-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
