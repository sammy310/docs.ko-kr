---
description: '자세히 알아보기: ICorDebugProcess4 인터페이스'
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
ms.openlocfilehash: 16c7f3fbd1a79b1406fe0c19a9d922964667a2a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650003"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="4928e-103">ICorDebugProcess4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4928e-103">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="4928e-104">Out-of-process 실행 제어에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4928e-104">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="4928e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4928e-105">Methods</span></span>

| <span data-ttu-id="4928e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4928e-106">Method</span></span>                                                                 | <span data-ttu-id="4928e-107">설명</span><span class="sxs-lookup"><span data-stu-id="4928e-107">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="4928e-108">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="4928e-108">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="4928e-109">ICorDebug 파이프라인에 out of process 디버거가 디버기의의 실행을 계속 진행 중임을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4928e-109">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="4928e-110">설명</span><span class="sxs-lookup"><span data-stu-id="4928e-110">Remarks</span></span>

<span data-ttu-id="4928e-111">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4928e-111">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="4928e-112">그러나 `IUnknown` `E930C679-78AF-4953-8AB7-B0AABF0F9F80` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4928e-112">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="4928e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4928e-113">Requirements</span></span>

<span data-ttu-id="4928e-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4928e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="4928e-115">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="4928e-115">**Header:** None</span></span>

<span data-ttu-id="4928e-116">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="4928e-116">**Library:** None</span></span>

<span data-ttu-id="4928e-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4928e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4928e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4928e-118">See also</span></span>

- [<span data-ttu-id="4928e-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4928e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4928e-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="4928e-120">Debugging</span></span>](index.md)
