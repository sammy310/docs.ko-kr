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
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213584"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="efb94-102">ICorDebugProcess4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efb94-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="efb94-103">Out-of-process 실행 제어에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb94-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="efb94-104">메서드</span><span class="sxs-lookup"><span data-stu-id="efb94-104">Methods</span></span>

| <span data-ttu-id="efb94-105">메서드</span><span class="sxs-lookup"><span data-stu-id="efb94-105">Method</span></span>                                                                 | <span data-ttu-id="efb94-106">설명</span><span class="sxs-lookup"><span data-stu-id="efb94-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="efb94-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="efb94-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="efb94-108">ICorDebug 파이프라인에 out of process 디버거가 디버기의의 실행을 계속 진행 중임을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="efb94-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="efb94-109">설명</span><span class="sxs-lookup"><span data-stu-id="efb94-109">Remarks</span></span>

<span data-ttu-id="efb94-110">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb94-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="efb94-111">그러나 `IUnknown` `E930C679-78AF-4953-8AB7-B0AABF0F9F80` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="efb94-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="efb94-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="efb94-112">Requirements</span></span>

<span data-ttu-id="efb94-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb94-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="efb94-114">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="efb94-114">**Header:** None</span></span>

<span data-ttu-id="efb94-115">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="efb94-115">**Library:** None</span></span>

<span data-ttu-id="efb94-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="efb94-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efb94-117">See also</span></span>

- [<span data-ttu-id="efb94-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efb94-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="efb94-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="efb94-119">Debugging</span></span>](index.md)
