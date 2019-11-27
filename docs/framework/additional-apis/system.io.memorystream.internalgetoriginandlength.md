---
title: MemoryStream InternalGetOriginAndLength 메서드 (System.IO)
author: mairaw
ms.author: mairaw
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d2bfa087fe2fb247f963cfa687c27056363d5696
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284044"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a><span data-ttu-id="28230-102">MemoryStream InternalGetOriginAndLength 메서드</span><span class="sxs-lookup"><span data-stu-id="28230-102">MemoryStream.InternalGetOriginAndLength method</span></span>

<span data-ttu-id="28230-103">원본 및 메모리 스트림의 길이에 대 한 내부 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28230-103">Gets the internal values of origin and length of the memory stream.</span></span>

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a><span data-ttu-id="28230-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28230-104">Parameters</span></span>

- <span data-ttu-id="28230-105">`origin` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="28230-105">`origin` <xref:System.Int32></span></span>\
  <span data-ttu-id="28230-106">이 메서드가 반환 될 때 새 <xref:System.IO.MemoryStream> 개체를 만들 때 지정 된 바이트 배열의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="28230-106">When this method returns, the offset of the byte array specified when creating a new <xref:System.IO.MemoryStream> object.</span></span> <span data-ttu-id="28230-107"><xref:System.IO.MemoryStream>에서 바이트 배열을 만든 경우 0을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="28230-107">Contains 0 if the byte array was created by <xref:System.IO.MemoryStream>.</span></span>

- <span data-ttu-id="28230-108">`length` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="28230-108">`length` <xref:System.Int32></span></span>\
  <span data-ttu-id="28230-109">이 메서드가 반환 될 때 메모리 스트림 내의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="28230-109">When this method returns, the number of bytes within the memory stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="28230-110">설명</span><span class="sxs-lookup"><span data-stu-id="28230-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="28230-111">`MemoryStream.InternalGetOriginAndLength` 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28230-111">The `MemoryStream.InternalGetOriginAndLength` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="28230-112">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28230-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="28230-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28230-113">Requirements</span></span>

<span data-ttu-id="28230-114">**네임스페이스:** <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="28230-114">**Namespace:** <xref:System.IO></span></span>

<span data-ttu-id="28230-115">**어셈블리:** mscorlib.dll (mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="28230-115">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="28230-116">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28230-116">**.NET Framework versions:** Available since 2.0.</span></span>
