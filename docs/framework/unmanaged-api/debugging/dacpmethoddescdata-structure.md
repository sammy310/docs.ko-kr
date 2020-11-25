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
ms.openlocfilehash: dcf01c00a106c131646a16597dca4092a06c5983
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723066"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="9483b-102">DacpMethodDescData 구조체</span><span class="sxs-lookup"><span data-stu-id="9483b-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="9483b-103">메서드의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9483b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9483b-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="9483b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9483b-105">Members</span></span>

| <span data-ttu-id="9483b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9483b-106">Member</span></span>                       | <span data-ttu-id="9483b-107">설명</span><span class="sxs-lookup"><span data-stu-id="9483b-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="9483b-108">런타임에 메서드의 지정 된 인스턴스화에 사용할 수 있는 네이티브 코드가 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="9483b-109">경량 코드 생성을 통해 메서드가 동적으로 생성 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="9483b-110">메서드 테이블의 메서드 슬롯 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="9483b-111">메서드의 초기 네이티브 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="9483b-112">런타임에서 내부적으로 사용 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="9483b-113">런타임에 대 한 포인터 `MethodDesc` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="9483b-114">런타임에서 메서드를 추적 하기 위해 내부적으로 사용 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="9483b-115">모듈 정보에 대 한 런타임에서 내부적으로 사용 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="9483b-116">지정 된 메서드와 연결 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="9483b-117">런타임에서 내부적으로 사용 하는 가비지 컬렉션 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="9483b-118">런타임에서 내부적으로 사용 하는 가비지 컬렉션 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="9483b-119">메서드가 동적 이면 런타임에서 정보 추적을 위해 내부적으로이 버퍼를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="9483b-120">네이티브 코드 주소가 지정 된 경우 요청당 구조를 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="9483b-121">메서드의 최신 계측 된 버전에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="9483b-122">요청 된 기본 주소에 대 한 정보를 Rejit 합니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="9483b-123">메서드가 계측을 통해 rejitted 된 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="9483b-124">설명</span><span class="sxs-lookup"><span data-stu-id="9483b-124">Remarks</span></span>

<span data-ttu-id="9483b-125">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9483b-126">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9483b-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="9483b-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9483b-127">Requirements</span></span>

<span data-ttu-id="9483b-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9483b-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9483b-129">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="9483b-129">**Header:** None</span></span>  
<span data-ttu-id="9483b-130">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="9483b-130">**Library:** None</span></span>  
<span data-ttu-id="9483b-131">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9483b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9483b-132">참조</span><span class="sxs-lookup"><span data-stu-id="9483b-132">See also</span></span>

- [<span data-ttu-id="9483b-133">디버깅</span><span class="sxs-lookup"><span data-stu-id="9483b-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="9483b-134">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="9483b-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="9483b-135">공통 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9483b-135">Common Data Types</span></span>](../common-data-types-unmanaged-api-reference.md)
