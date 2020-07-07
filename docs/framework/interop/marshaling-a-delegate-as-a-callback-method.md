---
title: 콜백 메서드로 대리자 마샬링
description: 대리자를 콜백 메서드로 마샬링하는 방법을 알아봅니다. 함수 포인터가 필요한 관리되지 않는 함수에 대리자를 전달하는 방법의 예제를 살펴봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
ms.openlocfilehash: bf9ef3b9d48c0869dcc96820c3a2fb6fb608479e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618950"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="968cc-104">콜백 메서드로 대리자 마샬링</span><span class="sxs-lookup"><span data-stu-id="968cc-104">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="968cc-105">이 샘플에서는 함수 포인터가 필요한 관리되지 않는 함수에 대리자를 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-105">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="968cc-106">대리자는 메서드에 대한 참조를 보유할 수 있는 클래스이고 형식이 안전한 함수 포인터나 콜백 함수에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-106">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>

> [!NOTE]
> <span data-ttu-id="968cc-107">호출에서 대리자를 사용하면 공용 언어 런타임에서 대리자가 해당 호출 기간 동안 가비지 수집되지 않게 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-107">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="968cc-108">그러나 관리되지 않는 함수에서 호출이 완료된 후 사용하기 위해 대리자를 저장하는 경우 관리되지 않는 함수가 대리자를 완료할 때까지 직접 가비지 수집이 수행되지 않게 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-108">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="968cc-109">자세한 내용은 [HandleRef 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) 및 [GCHandle 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="968cc-109">For more information, see the [HandleRef Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) and [GCHandle Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span></span>

<span data-ttu-id="968cc-110">Callback 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-110">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="968cc-111">`TestCallBack` - PinvokeLib.dll에서 내보냄</span><span class="sxs-lookup"><span data-stu-id="968cc-111">`TestCallBack` exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestCallBack(FPTR pf, int value);
    ```

- <span data-ttu-id="968cc-112">`TestCallBack2` - PinvokeLib.dll에서 내보냄</span><span class="sxs-lookup"><span data-stu-id="968cc-112">`TestCallBack2` exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestCallBack2(FPTR2 pf2, char* value);
    ```

<span data-ttu-id="968cc-113">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll)은 앞에 나열된 함수의 구현을 포함하는 관리되지 않는 사용자 지정 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-113">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>

<span data-ttu-id="968cc-114">이 샘플에서 `NativeMethods` 클래스에는 `TestCallBack` 및 `TestCallBack2` 메서드의 관리되는 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-114">In this sample, the `NativeMethods` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="968cc-115">두 메서드 모두 대리자를 매개 변수로 콜백 함수에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-115">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="968cc-116">대리자의 시그니처는 대리자가 참조하는 메서드의 시그니처와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-116">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="968cc-117">예를 들어 `FPtr` 및 `FPtr2` 대리자는 `DoSomething` 및 `DoSomething2` 메서드에 동일한 시그니처가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="968cc-117">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>

## <a name="declaring-prototypes"></a><span data-ttu-id="968cc-118">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="968cc-118">Declaring Prototypes</span></span>
[!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
[!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
[!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]

## <a name="calling-functions"></a><span data-ttu-id="968cc-119">함수 호출</span><span class="sxs-lookup"><span data-stu-id="968cc-119">Calling Functions</span></span>
[!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
[!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
[!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]

## <a name="see-also"></a><span data-ttu-id="968cc-120">참조</span><span class="sxs-lookup"><span data-stu-id="968cc-120">See also</span></span>

- <span data-ttu-id="968cc-121">[기타 마샬링 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="968cc-121">[Miscellaneous Marshaling Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span></span>
- [<span data-ttu-id="968cc-122">플랫폼 호출 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="968cc-122">Platform Invoke Data Types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="968cc-123">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="968cc-123">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
