---
title: 플랫폼 호출을 사용하여 데이터 마샬링
ms.date: 03/20/2019
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
ms.openlocfilehash: b8c4e9d835db044912d1cbed92a14dd05e7de658
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113937"
---
# <a name="marshaling-data-with-platform-invoke"></a><span data-ttu-id="7cbaf-102">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="7cbaf-102">Marshaling Data with Platform Invoke</span></span>

<span data-ttu-id="7cbaf-103">관리되지 않는 라이브러리에서 내보낸 함수를 호출하려면 .NET Framework 애플리케이션의 관리 코드에 관리되지 않는 함수를 나타내는 함수 프로토타입이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-103">To call functions exported from an unmanaged library, a .NET Framework application requires a function prototype in managed code that represents the unmanaged function.</span></span> <span data-ttu-id="7cbaf-104">데이터를 제대로 마샬링하도록 플랫폼에서 호출할 수 있는 프로토타입을 만들려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-104">To create a prototype that enables platform invoke to marshal data correctly, you must do the following:</span></span>

- <span data-ttu-id="7cbaf-105">관리 코드의 정적 함수 또는 메서드에 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-105">Apply the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to the static function or method in managed code.</span></span>

- <span data-ttu-id="7cbaf-106">관리되지 않은 데이터 형식 대신 관리되는 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-106">Substitute managed data types for unmanaged data types.</span></span>

<span data-ttu-id="7cbaf-107">관리되지 않는 함수와 함께 제공된 설명서를 사용하여 선택적 필드가 포함된 특성을 적용하고 관리되지 않는 형식 대신 관리되는 데이터 형식을 사용하는 방식으로 해당하는 관리되는 프로토타입을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-107">You can use the documentation supplied with an unmanaged function to construct an equivalent managed prototype by applying the attribute with its optional fields and substituting managed data types for unmanaged types.</span></span> <span data-ttu-id="7cbaf-108"><xref:System.Runtime.InteropServices.DllImportAttribute>를 적용하는 방법에 대한 자세한 내용은 [관리되지 않는 DLL 함수 사용](consuming-unmanaged-dll-functions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-108">For instructions about how to apply the <xref:System.Runtime.InteropServices.DllImportAttribute>, see [Consuming Unmanaged DLL Functions](consuming-unmanaged-dll-functions.md).</span></span>

<span data-ttu-id="7cbaf-109">이 섹션에서는 인수를 전달하고 관리되는 라이브러리를 통해 내보낸 함수에서 반환 값을 수신하기 위한 관리되는 함수 프로토타입을 만드는 방법을 보여 주는 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-109">This section provides samples that demonstrate how to create managed function prototypes for passing arguments to and receiving return values from functions exported by unmanaged libraries.</span></span> <span data-ttu-id="7cbaf-110">샘플에서는 데이터를 명시적으로 마샬링하도록 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성과 <xref:System.Runtime.InteropServices.Marshal> 클래스를 사용하는 시기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-110">The samples also demonstrate when to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute and the <xref:System.Runtime.InteropServices.Marshal> class to explicitly marshal data.</span></span>

## <a name="platform-invoke-data-types"></a><span data-ttu-id="7cbaf-111">플랫폼 호출 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7cbaf-111">Platform invoke data types</span></span>

<span data-ttu-id="7cbaf-112">다음 표에는 Windows API 및 C 스타일 함수에서 사용되는 데이터 형식이 나와있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-112">The following table lists data types used in the Windows APIs and C-style functions.</span></span> <span data-ttu-id="7cbaf-113">대부분 관리되지 않는 라이브러리에는 이들 데이터 형식을 매개 변수 및 반환 값으로 전달하는 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-113">Many unmanaged libraries contain functions that pass these data types as parameters and return values.</span></span> <span data-ttu-id="7cbaf-114">세 번째 열에는 관리 코드에서 사용하는 것에 해당하는 .NET Framework 기본 제공 값 형식 또는 클래스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-114">The third column lists the corresponding .NET Framework built-in value type or class that you use in managed code.</span></span> <span data-ttu-id="7cbaf-115">경우에 따라 표에 나열된 형식 대신 같은 크기의 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-115">In some cases, you can substitute a type of the same size for the type listed in the table.</span></span>

|<span data-ttu-id="7cbaf-116">Windows API의 관리되지 않는 형식</span><span class="sxs-lookup"><span data-stu-id="7cbaf-116">Unmanaged type in Windows APIs</span></span>|<span data-ttu-id="7cbaf-117">관리되지 않는 C 언어 형식</span><span class="sxs-lookup"><span data-stu-id="7cbaf-117">Unmanaged C language type</span></span>|<span data-ttu-id="7cbaf-118">관리형 형식</span><span class="sxs-lookup"><span data-stu-id="7cbaf-118">Managed type</span></span>|<span data-ttu-id="7cbaf-119">설명</span><span class="sxs-lookup"><span data-stu-id="7cbaf-119">Description</span></span>|
|--------------------------------|-------------------------------|------------------------|-----------------|
|`VOID`|`void`|<xref:System.Void?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-120">값을 반환하지 않는 함수에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-120">Applied to a function that does not return a value.</span></span>|
|`HANDLE`|`void *`|<span data-ttu-id="7cbaf-121"><xref:System.IntPtr?displayProperty=nameWithType> 또는 <xref:System.UIntPtr?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7cbaf-121"><xref:System.IntPtr?displayProperty=nameWithType> or <xref:System.UIntPtr?displayProperty=nameWithType></span></span>|<span data-ttu-id="7cbaf-122">32비트 Windows 운영 체제의 32비트, 64비트 운영 체제의 64비트.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-122">32 bits on 32-bit Windows operating systems, 64 bits on 64-bit Windows operating systems.</span></span>|
|`BYTE`|`unsigned char`|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-123">8비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-123">8 bits</span></span>|
|`SHORT`|`short`|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-124">16비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-124">16 bits</span></span>|
|`WORD`|`unsigned short`|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-125">16비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-125">16 bits</span></span>|
|`INT`|`int`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-126">32비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-126">32 bits</span></span>|
|`UINT`|`unsigned int`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-127">32비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-127">32 bits</span></span>|
|`LONG`|`long`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-128">32비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-128">32 bits</span></span>|
|`BOOL`|`long`|<span data-ttu-id="7cbaf-129"><xref:System.Boolean?displayProperty=nameWithType> 또는 <xref:System.Int32?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7cbaf-129"><xref:System.Boolean?displayProperty=nameWithType> or <xref:System.Int32?displayProperty=nameWithType></span></span>|<span data-ttu-id="7cbaf-130">32비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-130">32 bits</span></span>|
|`DWORD`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-131">32비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-131">32 bits</span></span>|
|`ULONG`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-132">32비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-132">32 bits</span></span>|
|`CHAR`|`char`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-133">ANSI로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-133">Decorate with ANSI.</span></span>|
|`WCHAR`|`wchar_t`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-134">유니코드로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-134">Decorate with Unicode.</span></span>|
|`LPSTR`|`char *`|<span data-ttu-id="7cbaf-135"><xref:System.String?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7cbaf-135"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="7cbaf-136">ANSI로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-136">Decorate with ANSI.</span></span>|
|`LPCSTR`|`const char *`|<span data-ttu-id="7cbaf-137"><xref:System.String?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7cbaf-137"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="7cbaf-138">ANSI로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-138">Decorate with ANSI.</span></span>|
|`LPWSTR`|`wchar_t *`|<span data-ttu-id="7cbaf-139"><xref:System.String?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7cbaf-139"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="7cbaf-140">유니코드로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-140">Decorate with Unicode.</span></span>|
|`LPCWSTR`|`const wchar_t *`|<span data-ttu-id="7cbaf-141"><xref:System.String?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7cbaf-141"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="7cbaf-142">유니코드로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-142">Decorate with Unicode.</span></span>|
|`FLOAT`|`float`|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-143">32비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-143">32 bits</span></span>|
|`DOUBLE`|`double`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="7cbaf-144">64비트</span><span class="sxs-lookup"><span data-stu-id="7cbaf-144">64 bits</span></span>|

<span data-ttu-id="7cbaf-145">Visual Basic, C# 및 C++의 해당하는 형식에 대해서는 [.NET Framework 클래스 라이브러리 소개](../../standard/class-library-overview.md#system-namespace)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-145">For corresponding types in Visual Basic, C#, and C++, see the [Introduction to the .NET Framework Class Library](../../standard/class-library-overview.md#system-namespace).</span></span>

## <a name="pinvokelibdll"></a><span data-ttu-id="7cbaf-146">PinvokeLib.dll</span><span class="sxs-lookup"><span data-stu-id="7cbaf-146">PinvokeLib.dll</span></span>

<span data-ttu-id="7cbaf-147">다음 코드에서는 Pinvoke.dll에서 제공되는 라이브러리 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-147">The following code defines the library functions provided by Pinvoke.dll.</span></span> <span data-ttu-id="7cbaf-148">이 섹션에 설명된 대부분 샘플이 이 라이브러리를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbaf-148">Many samples described in this section call this library.</span></span>

### <a name="example"></a><span data-ttu-id="7cbaf-149">예제</span><span class="sxs-lookup"><span data-stu-id="7cbaf-149">Example</span></span>

[!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]

[!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]
