---
title: ICorDebugProcess4 인터페이스
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948808"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="ef003-102">ICorDebugProcess4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef003-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="ef003-103">프로세스 실행 제어가 부족에 대 한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef003-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="ef003-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ef003-104">Methods</span></span>

| <span data-ttu-id="ef003-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ef003-105">Method</span></span>                                                                 | <span data-ttu-id="ef003-106">설명</span><span class="sxs-lookup"><span data-stu-id="ef003-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="ef003-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="ef003-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="ef003-108">디버거 프로세스의 디버기의 실행을 계속 되는 ICorDebug 파이프라인에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ef003-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ef003-109">설명</span><span class="sxs-lookup"><span data-stu-id="ef003-109">Remarks</span></span>

<span data-ttu-id="ef003-110">이 인터페이스는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef003-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="ef003-111">그러나 COM 인터페이스에서 파생 되는 것 `IUnknown` GUID를 사용 하 여 `E930C679-78AF-4953-8AB7-B0AABF0F9F80` 일반적인 COM 메커니즘을 통해 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef003-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ef003-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef003-112">Requirements</span></span>

<span data-ttu-id="ef003-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef003-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ef003-114">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="ef003-114">**Header:** None</span></span>

<span data-ttu-id="ef003-115">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="ef003-115">**Library:** None</span></span>

<span data-ttu-id="ef003-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef003-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ef003-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="ef003-117">See also</span></span>

- [<span data-ttu-id="ef003-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef003-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ef003-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="ef003-119">Debugging</span></span>](index.md)
