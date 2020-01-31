---
title: 디버깅 구조체
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: a18094fb2621478dbdb4bbf672df436234112ed0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793749"
---
# <a name="debugging-structures"></a><span data-ttu-id="2afc2-102">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="2afc2-102">Debugging Structures</span></span>

<span data-ttu-id="2afc2-103">이 섹션에서는 디버깅 API에서 사용하는 관리되지 않는 구조체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2afc2-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2afc2-104">In This Section</span></span>
 <span data-ttu-id="2afc2-105">[CLRDATA_ADDRESS_RANGE 구조체](clrdata-address-range-structure.md) 주소 범위를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-105">[CLRDATA_ADDRESS_RANGE Structure](clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="2afc2-106">[CLRDATA_IL_ADDRESS_MAP 구조체](clrdata-il-address-map-structure.md) 매핑을 처리할 IL을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-106">[CLRDATA_IL_ADDRESS_MAP Structure](clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="2afc2-107">[CLR_DEBUGGING_VERSION 구조체](clr-debugging-version-structure.md) 디버깅 목적으로 CLR (공용 언어 런타임)의 제품 버전을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-107">[CLR_DEBUGGING_VERSION Structure](clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="2afc2-108">[CodeChunkInfo 구조체](codechunkinfo-structure.md) 메모리의 단일 코드 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-108">[CodeChunkInfo Structure](codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="2afc2-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) 스레드의 프레임에서 현재 활성화 된 함수에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="2afc2-110">[COR_ARRAY_LAYOUT 구조체](cor-array-layout-structure.md) 메모리에 있는 배열 개체의 레이아웃에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-110">[COR_ARRAY_LAYOUT Structure](cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="2afc2-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) MSIL (Microsoft 중간 언어) 코드를 네이티브 코드에 매핑하는 데 사용 되는 오프셋을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="2afc2-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) 코드 범위에 대 한 오프셋 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="2afc2-113">[COR_FIELD 구조체](cor-field-structure.md) 개체의 필드에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-113">[COR_FIELD Structure](cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="2afc2-114">[COR_GC_REFERENCE 구조체](cor-gc-reference-structure.md) 가비지 수집 되는 개체에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-114">[COR_GC_REFERENCE Structure](cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="2afc2-115">[COR_HEAPINFO 구조체](cor-heapinfo-structure.md) 열거 가능한 지 여부를 비롯 하 여 가비지 컬렉션 힙에 대 한 일반 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-115">[COR_HEAPINFO Structure](cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="2afc2-116">[COR_HEAPOBJECT 구조체](cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-116">[COR_HEAPOBJECT Structure](cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="2afc2-117">[COR_IL_MAP](cor-il-map-structure.md) 함수의 상대 오프셋에 대 한 변경 내용을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="2afc2-118">[COR_SEGMENT 구조체](cor-segment-structure.md) 관리 되는 힙의 메모리 영역에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-118">[COR_SEGMENT Structure](cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="2afc2-119">[COR_TYPEID 구조체](cor-typeid-structure.md) 형식 식별자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-119">[COR_TYPEID Structure](cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="2afc2-120">[COR_TYPE_LAYOUT 구조체](cor-type-layout-structure.md) 메모리에 있는 개체의 레이아웃에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-120">[COR_TYPE_LAYOUT Structure](cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="2afc2-121">[COR_VERSION](cor-version-structure.md) 공용 언어 런타임의 네 부분으로 구성 된 표준 버전 번호를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="2afc2-122">[CorDebugBlockingObject 구조체](cordebugblockingobject-structure.md) 스레드를 차단 하는 개체와 스레드가 차단 되는 이유를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-122">[CorDebugBlockingObject Structure](cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="2afc2-123">[CorDebugEHClause 구조체](cordebugehclause-structure.md) 지정 된 IL (중간 언어) 부분에 대 한 EH (예외 처리) 절을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-123">[CorDebugEHClause Structure](cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="2afc2-124">[Cordebugexceptionobjectstackframe 구조체](cordebugexceptionobjectstackframe-structure.md) 예외 개체의 스택 프레임 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-124">[CorDebugExceptionObjectStackFrame Structure](cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="2afc2-125">[CorDebugGuidToTypeMapping 구조체](cordebugguidtotypemapping-structure.md) Windows 런타임 GUID를 해당 [ICorDebugType](icordebugtype-interface.md) 개체에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-125">[CorDebugGuidToTypeMapping Structure](cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="2afc2-126">[DacpGetModuleAddress 구조체](dacpgetmoduleaddress-structure.md) 모듈 주소 요청에 대 한 컨테이너를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-126">[DacpGetModuleAddress Structure](dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="2afc2-127">[DacpMethodDescData 구조체](dacpmethoddescdata-structure.md) 메서드의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-127">[DacpMethodDescData Structure](dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="2afc2-128">[DacpModuleData 구조체](dacpmoduledata-structure.md) 모듈의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-128">[DacpModuleData Structure](dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="2afc2-129">[DacpReJitData 구조체](dacprejitdata-structure.md) 지정 된 프로파일러 계측 된 메서드에 대 한 기본 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-129">[DacpReJitData Structure](dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="2afc2-130">[StackTrace_SimpleContext 구조체](stacktrace-simplecontext-structure.md) 전체 `CONTEXT` 구조 대신 사용할 수 있는 간단한 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2afc2-130">[StackTrace_SimpleContext Structure](stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="2afc2-131">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="2afc2-131">Related Sections</span></span>

 [<span data-ttu-id="2afc2-132">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="2afc2-132">Debugging Coclasses</span></span>](debugging-coclasses.md)

 [<span data-ttu-id="2afc2-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2afc2-133">Debugging Interfaces</span></span>](debugging-interfaces.md)

 [<span data-ttu-id="2afc2-134">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="2afc2-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)

 [<span data-ttu-id="2afc2-135">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="2afc2-135">Debugging Enumerations</span></span>](debugging-enumerations.md)

 [<span data-ttu-id="2afc2-136">디버깅</span><span class="sxs-lookup"><span data-stu-id="2afc2-136">Debugging</span></span>](index.md)
