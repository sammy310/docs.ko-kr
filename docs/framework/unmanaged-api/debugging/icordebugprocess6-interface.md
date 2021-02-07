---
description: '자세히 알아보기: ICorDebugProcess6 인터페이스'
title: ICorDebugProcess6 인터페이스
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: f303670d0667a80507bc623f9af037759fdde463
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691460"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="29c3f-103">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29c3f-103">ICorDebugProcess6 Interface</span></span>

<span data-ttu-id="29c3f-104">네이티브 예외 디버그 이벤트에서 인코딩되는 관리되는 디버그 이벤트 디코딩, 가상 모듈 분할 등의 기능을 사용할 수 있도록 ICorDebugProcess 인터페이스를 논리적으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-104">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29c3f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="29c3f-105">Methods</span></span>  
  
|<span data-ttu-id="29c3f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="29c3f-106">Method</span></span>|<span data-ttu-id="29c3f-107">설명</span><span class="sxs-lookup"><span data-stu-id="29c3f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29c3f-108">DecodeEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="29c3f-108">DecodeEvent Method</span></span>](icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="29c3f-109">특수하게 작성된 네이티브 예외 디버그 이벤트의 페이로드에서 캡슐화된 관리되는 디버그 이벤트를 디코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-109">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="29c3f-110">EnableVirtualModuleSplitting 메서드</span><span class="sxs-lookup"><span data-stu-id="29c3f-110">EnableVirtualModuleSplitting Method</span></span>](icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="29c3f-111">가상 모듈 분할을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-111">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="29c3f-112">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="29c3f-112">GetCode Method</span></span>](icordebugprocess6-getcode-method.md)|<span data-ttu-id="29c3f-113">특정 코드 주소에서 관리 코드에 대한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-113">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="29c3f-114">GetExportStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="29c3f-114">GetExportStepInfo Method</span></span>](icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="29c3f-115">관리 코드를 단계별로 실행할 수 있도록 런타임에 내보낸 함수에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-115">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="29c3f-116">MarkDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="29c3f-116">MarkDebuggerAttached Method</span></span>](icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="29c3f-117">.NET Framework 클래스 라이브러리의 <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> 메서드가 `true`를 반환하도록 디버기의 내부 상태를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-117">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="29c3f-118">ProcessStateChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="29c3f-118">ProcessStateChanged Method</span></span>](icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="29c3f-119">프로세스가 실행 중임을 [ICorDebug](icordebug-interface.md) 에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-119">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29c3f-120">설명</span><span class="sxs-lookup"><span data-stu-id="29c3f-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29c3f-121">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-121">The interface is available with .NET Native only.</span></span> <span data-ttu-id="29c3f-122">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="29c3f-122">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29c3f-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29c3f-123">Requirements</span></span>  

 <span data-ttu-id="29c3f-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29c3f-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c3f-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29c3f-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29c3f-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29c3f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29c3f-127">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c3f-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c3f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29c3f-128">See also</span></span>

- [<span data-ttu-id="29c3f-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29c3f-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="29c3f-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="29c3f-130">Debugging</span></span>](index.md)
