---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo 메서드
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
ms.openlocfilehash: a6c32b72c5924399aeb13d56ddf9242fe7990f35
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379315"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="cb18f-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="cb18f-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>

<span data-ttu-id="cb18f-103">제네릭 사전 맵을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-103">Retrieves a generic dictionary map.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb18f-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb18f-104">Syntax</span></span>

```cpp
HRESULT GetGenericDictionaryInfo(
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="cb18f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb18f-105">Parameters</span></span>

`ppMemoryBuffer`\
<span data-ttu-id="cb18f-106">제한이 제네릭 사전 맵을 포함 하는 [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="cb18f-107">자세한 내용은 주의 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb18f-107">See the Remarks section for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb18f-108">설명</span><span class="sxs-lookup"><span data-stu-id="cb18f-108">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="cb18f-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-109">This method is available with .NET Native only.</span></span>

<span data-ttu-id="cb18f-110">맵은 두 개의 최상위 섹션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-110">The map consists of two top-level sections:</span></span>

- <span data-ttu-id="cb18f-111">이 맵에 포함 된 모든 사전의 RVA (상대 가상 주소)를 포함 하는 [디렉터리](#Directory) 입니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>

- <span data-ttu-id="cb18f-112">개체 인스턴스화 정보를 포함 하는 바이트 정렬 [힙](#Heap)</span><span class="sxs-lookup"><span data-stu-id="cb18f-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="cb18f-113">마지막 디렉터리 항목 후에 즉시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-113">It starts immediately after the last directory entry.</span></span>

<a name="Directory"></a>

## <a name="the-directory"></a><span data-ttu-id="cb18f-114">디렉터리</span><span class="sxs-lookup"><span data-stu-id="cb18f-114">The Directory</span></span>

<span data-ttu-id="cb18f-115">디렉터리의 각 항목은 힙 내부의 오프셋을 나타냅니다. 즉, 힙의 시작 부분에 상대적인 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="cb18f-116">개별 항목의 값이 반드시 고유할 필요는 없습니다. 여러 디렉터리 항목이 힙의 동일한 오프셋을 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>

<span data-ttu-id="cb18f-117">제네릭 사전 맵의 디렉터리 부분은 다음과 같은 구조로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-117">The directory portion of the generic dictionary map has the following structure:</span></span>

- <span data-ttu-id="cb18f-118">처음 4바이트에는 사전 항목 수(즉, 사전의 상대 가상 주소 수)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="cb18f-119">이 값은 *N*으로 참조 합니다. 상위 비트가 설정 된 경우 항목은 상대 가상 주소를 기준으로 오름차순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>

- <span data-ttu-id="cb18f-120">*N* 디렉터리 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-120">The *N* directory entries follow.</span></span> <span data-ttu-id="cb18f-121">각 항목은 4바이트 세그먼트 2개인 8바이트로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>

  - <span data-ttu-id="cb18f-122">바이트 0-3: RVA, 사전의 상대 가상 주소</span><span class="sxs-lookup"><span data-stu-id="cb18f-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>

  - <span data-ttu-id="cb18f-123">바이트 4-7: 오프셋, 힙의 시작 부분에 상대적인 오프셋</span><span class="sxs-lookup"><span data-stu-id="cb18f-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>

<a name="Heap"></a>

## <a name="the-heap"></a><span data-ttu-id="cb18f-124">힙</span><span class="sxs-lookup"><span data-stu-id="cb18f-124">The Heap</span></span>

<span data-ttu-id="cb18f-125">스트림 판독기는 디렉터리 크기+4에서 스트림 길이를 빼서 힙 크기를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="cb18f-126">즉, 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-126">In other words:</span></span>

```csharp
Heap Size = Stream.Length – (Directory Size + 4)
```

<span data-ttu-id="cb18f-127">여기서 디렉터리 크기는 `N * 8`입니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-127">where the directory size is `N * 8`.</span></span>

<span data-ttu-id="cb18f-128">힙의 각 인스턴스화 정보 항목 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-128">The format for each instantiation information item on the heap is:</span></span>

- <span data-ttu-id="cb18f-129">압축된 ECMA 메타데이터 형식에서 이 인스턴스화 정보 항목의 길이(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="cb18f-130">이 길이 정보는 값에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-130">The value excludes this length information.</span></span>

- <span data-ttu-id="cb18f-131">압축 된 ECMA 메타 데이터 형식의 제네릭 인스턴스화 형식 또는 *T*의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>

- <span data-ttu-id="cb18f-132">각각 ECMA 형식 서명 형식으로 표현 되는 *T* 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-132">*T* types, each represented in ECMA type signature format.</span></span>

<span data-ttu-id="cb18f-133">각 힙 요소의 길이를 포함하면 힙에 영향을 주지 않고 디렉터리 섹션을 간단하게 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb18f-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb18f-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb18f-134">Requirements</span></span>

<span data-ttu-id="cb18f-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb18f-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="cb18f-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb18f-136">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="cb18f-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb18f-137">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="cb18f-138">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb18f-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cb18f-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb18f-139">See also</span></span>

- [<span data-ttu-id="cb18f-140">ICorDebugSymbolProvider2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb18f-140">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="cb18f-141">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb18f-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
