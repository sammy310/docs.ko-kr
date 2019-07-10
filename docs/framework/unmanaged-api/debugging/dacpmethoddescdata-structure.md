---
title: DacpMethodDescData 구조체
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 97079b824dbd0e056374af4173e49304babd6c32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739140"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="8baa1-102">DacpMethodDescData 구조체</span><span class="sxs-lookup"><span data-stu-id="8baa1-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="8baa1-103">메서드의 런타임 정보에 대 한 전송 버퍼를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8baa1-104">구문</span><span class="sxs-lookup"><span data-stu-id="8baa1-104">Syntax</span></span>

```cpp
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a><span data-ttu-id="8baa1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8baa1-105">Members</span></span>

| <span data-ttu-id="8baa1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8baa1-106">Member</span></span>                       | <span data-ttu-id="8baa1-107">설명</span><span class="sxs-lookup"><span data-stu-id="8baa1-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="8baa1-108">런타임은 메서드의 지정된 인스턴스화에 대 한 사용 가능한 네이티브 코드에 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="8baa1-109">경량 코드 생성을 통해 메서드를 동적으로 생성 하는 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="8baa1-110">메서드의 메서드 테이블의 슬롯 번호.</span><span class="sxs-lookup"><span data-stu-id="8baa1-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="8baa1-111">메서드의 초기 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="8baa1-112">런타임에서 내부적으로 사용 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="8baa1-113">에 대 한 포인터를 `MethodDesc` 런타임에서입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="8baa1-114">메서드를 추적 하는 런타임에서 내부적으로 사용 되는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="8baa1-115">모듈 정보에 대 한 런타임에 의해 내부적으로 사용 되는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="8baa1-116">지정된 된 메서드를 사용 하 여 연결 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="8baa1-117">런타임에서 내부적으로 사용 하는 가비지 컬렉션 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="8baa1-118">런타임에서 내부적으로 사용 하는 가비지 컬렉션 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="8baa1-119">메서드가 동적 이면 런타임에서이 버퍼 내부적으로 사용 정보 추적에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="8baa1-120">네이티브 코드 주소를 지정 하는 경우 요청당 구조를 채우는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="8baa1-121">계측 된 메서드는 최신 버전에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="8baa1-122">요청된 된 기본 주소에 대 한 Rejit 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="8baa1-123">메서드는 계측을 통해 rejitted 된 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="8baa1-124">설명</span><span class="sxs-lookup"><span data-stu-id="8baa1-124">Remarks</span></span>

<span data-ttu-id="8baa1-125">이 구조는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8baa1-126">를 사용 하려면 위에서 지정한 대로 구조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8baa1-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="8baa1-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8baa1-127">Requirements</span></span>
<span data-ttu-id="8baa1-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8baa1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8baa1-129">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="8baa1-129">**Header:** None</span></span>  
<span data-ttu-id="8baa1-130">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="8baa1-130">**Library:** None</span></span>  
<span data-ttu-id="8baa1-131">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8baa1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8baa1-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="8baa1-132">See also</span></span>

- [<span data-ttu-id="8baa1-133">디버깅</span><span class="sxs-lookup"><span data-stu-id="8baa1-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="8baa1-134">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="8baa1-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="8baa1-135">공통 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8baa1-135">Common Data Types</span></span>](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
