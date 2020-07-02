---
title: 플랫폼 호출을 사용하여 데이터 마샬링
description: .NET에서 플랫폼 호출을 사용하여 데이터를 마샬링합니다. Windows API 및 C 스타일 함수에 사용되는 데이터 형식의 목록을 확인하고 이러한 형식에 해당하는 .NET 관리형 형식을 찾습니다.
ms.date: 03/20/2019
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
ms.openlocfilehash: 27045790780c1eef9537bdf7e52deb579e2b467c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904106"
---
# <a name="marshaling-data-with-platform-invoke"></a><span data-ttu-id="23369-104">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="23369-104">Marshaling Data with Platform Invoke</span></span>

<span data-ttu-id="23369-105">관리되지 않는 라이브러리에서 내보낸 함수를 호출하려면 .NET Framework 애플리케이션의 관리 코드에 관리되지 않는 함수를 나타내는 함수 프로토타입이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-105">To call functions exported from an unmanaged library, a .NET Framework application requires a function prototype in managed code that represents the unmanaged function.</span></span> <span data-ttu-id="23369-106">데이터를 제대로 마샬링하도록 플랫폼에서 호출할 수 있는 프로토타입을 만들려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-106">To create a prototype that enables platform invoke to marshal data correctly, you must do the following:</span></span>

- <span data-ttu-id="23369-107">관리 코드의 정적 함수 또는 메서드에 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-107">Apply the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to the static function or method in managed code.</span></span>

- <span data-ttu-id="23369-108">관리되지 않은 데이터 형식 대신 관리되는 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-108">Substitute managed data types for unmanaged data types.</span></span>

<span data-ttu-id="23369-109">관리되지 않는 함수와 함께 제공된 설명서를 사용하여 선택적 필드가 포함된 특성을 적용하고 관리되지 않는 형식 대신 관리되는 데이터 형식을 사용하는 방식으로 해당하는 관리되는 프로토타입을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23369-109">You can use the documentation supplied with an unmanaged function to construct an equivalent managed prototype by applying the attribute with its optional fields and substituting managed data types for unmanaged types.</span></span> <span data-ttu-id="23369-110"><xref:System.Runtime.InteropServices.DllImportAttribute>를 적용하는 방법에 대한 자세한 내용은 [관리되지 않는 DLL 함수 사용](consuming-unmanaged-dll-functions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23369-110">For instructions about how to apply the <xref:System.Runtime.InteropServices.DllImportAttribute>, see [Consuming Unmanaged DLL Functions](consuming-unmanaged-dll-functions.md).</span></span>

<span data-ttu-id="23369-111">이 섹션에서는 인수를 전달하고 관리되는 라이브러리를 통해 내보낸 함수에서 반환 값을 수신하기 위한 관리되는 함수 프로토타입을 만드는 방법을 보여 주는 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-111">This section provides samples that demonstrate how to create managed function prototypes for passing arguments to and receiving return values from functions exported by unmanaged libraries.</span></span> <span data-ttu-id="23369-112">샘플에서는 데이터를 명시적으로 마샬링하도록 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성과 <xref:System.Runtime.InteropServices.Marshal> 클래스를 사용하는 시기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23369-112">The samples also demonstrate when to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute and the <xref:System.Runtime.InteropServices.Marshal> class to explicitly marshal data.</span></span>

## <a name="platform-invoke-data-types"></a><span data-ttu-id="23369-113">플랫폼 호출 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="23369-113">Platform invoke data types</span></span>

<span data-ttu-id="23369-114">다음 표에는 Windows API 및 C 스타일 함수에서 사용되는 데이터 형식이 나와있습니다.</span><span class="sxs-lookup"><span data-stu-id="23369-114">The following table lists data types used in the Windows APIs and C-style functions.</span></span> <span data-ttu-id="23369-115">대부분 관리되지 않는 라이브러리에는 이들 데이터 형식을 매개 변수 및 반환 값으로 전달하는 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23369-115">Many unmanaged libraries contain functions that pass these data types as parameters and return values.</span></span> <span data-ttu-id="23369-116">세 번째 열에는 관리 코드에서 사용하는 것에 해당하는 .NET Framework 기본 제공 값 형식 또는 클래스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="23369-116">The third column lists the corresponding .NET Framework built-in value type or class that you use in managed code.</span></span> <span data-ttu-id="23369-117">경우에 따라 표에 나열된 형식 대신 같은 크기의 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23369-117">In some cases, you can substitute a type of the same size for the type listed in the table.</span></span>

|<span data-ttu-id="23369-118">Windows API의 관리되지 않는 형식</span><span class="sxs-lookup"><span data-stu-id="23369-118">Unmanaged type in Windows APIs</span></span>|<span data-ttu-id="23369-119">관리되지 않는 C 언어 형식</span><span class="sxs-lookup"><span data-stu-id="23369-119">Unmanaged C language type</span></span>|<span data-ttu-id="23369-120">관리형 형식</span><span class="sxs-lookup"><span data-stu-id="23369-120">Managed type</span></span>|<span data-ttu-id="23369-121">설명</span><span class="sxs-lookup"><span data-stu-id="23369-121">Description</span></span>|
|--------------------------------|-------------------------------|------------------------|-----------------|
|`VOID`|`void`|<xref:System.Void?displayProperty=nameWithType>|<span data-ttu-id="23369-122">값을 반환하지 않는 함수에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23369-122">Applied to a function that does not return a value.</span></span>|
|`HANDLE`|`void *`|<span data-ttu-id="23369-123"><xref:System.IntPtr?displayProperty=nameWithType> 또는 <xref:System.UIntPtr?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="23369-123"><xref:System.IntPtr?displayProperty=nameWithType> or <xref:System.UIntPtr?displayProperty=nameWithType></span></span>|<span data-ttu-id="23369-124">32비트 Windows 운영 체제의 32비트, 64비트 운영 체제의 64비트.</span><span class="sxs-lookup"><span data-stu-id="23369-124">32 bits on 32-bit Windows operating systems, 64 bits on 64-bit Windows operating systems.</span></span>|
|`BYTE`|`unsigned char`|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="23369-125">8비트</span><span class="sxs-lookup"><span data-stu-id="23369-125">8 bits</span></span>|
|`SHORT`|`short`|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="23369-126">16비트</span><span class="sxs-lookup"><span data-stu-id="23369-126">16 bits</span></span>|
|`WORD`|`unsigned short`|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="23369-127">16비트</span><span class="sxs-lookup"><span data-stu-id="23369-127">16 bits</span></span>|
|`INT`|`int`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="23369-128">32비트</span><span class="sxs-lookup"><span data-stu-id="23369-128">32 bits</span></span>|
|`UINT`|`unsigned int`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="23369-129">32비트</span><span class="sxs-lookup"><span data-stu-id="23369-129">32 bits</span></span>|
|`LONG`|`long`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="23369-130">32비트</span><span class="sxs-lookup"><span data-stu-id="23369-130">32 bits</span></span>|
|`BOOL`|`long`|<span data-ttu-id="23369-131"><xref:System.Boolean?displayProperty=nameWithType> 또는 <xref:System.Int32?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="23369-131"><xref:System.Boolean?displayProperty=nameWithType> or <xref:System.Int32?displayProperty=nameWithType></span></span>|<span data-ttu-id="23369-132">32비트</span><span class="sxs-lookup"><span data-stu-id="23369-132">32 bits</span></span>|
|`DWORD`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="23369-133">32비트</span><span class="sxs-lookup"><span data-stu-id="23369-133">32 bits</span></span>|
|`ULONG`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="23369-134">32비트</span><span class="sxs-lookup"><span data-stu-id="23369-134">32 bits</span></span>|
|`CHAR`|`char`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="23369-135">ANSI로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-135">Decorate with ANSI.</span></span>|
|`WCHAR`|`wchar_t`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="23369-136">유니코드로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-136">Decorate with Unicode.</span></span>|
|`LPSTR`|`char *`|<span data-ttu-id="23369-137"><xref:System.String?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="23369-137"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="23369-138">ANSI로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-138">Decorate with ANSI.</span></span>|
|`LPCSTR`|`const char *`|<span data-ttu-id="23369-139"><xref:System.String?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="23369-139"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="23369-140">ANSI로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-140">Decorate with ANSI.</span></span>|
|`LPWSTR`|`wchar_t *`|<span data-ttu-id="23369-141"><xref:System.String?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="23369-141"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="23369-142">유니코드로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-142">Decorate with Unicode.</span></span>|
|`LPCWSTR`|`const wchar_t *`|<span data-ttu-id="23369-143"><xref:System.String?displayProperty=nameWithType> 또는 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="23369-143"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="23369-144">유니코드로 데코레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-144">Decorate with Unicode.</span></span>|
|`FLOAT`|`float`|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="23369-145">32비트</span><span class="sxs-lookup"><span data-stu-id="23369-145">32 bits</span></span>|
|`DOUBLE`|`double`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="23369-146">64비트</span><span class="sxs-lookup"><span data-stu-id="23369-146">64 bits</span></span>|

<span data-ttu-id="23369-147">Visual Basic, C# 및 C++의 해당하는 형식에 대해서는 [.NET Framework 클래스 라이브러리 소개](../../standard/class-library-overview.md#system-namespace)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23369-147">For corresponding types in Visual Basic, C#, and C++, see the [Introduction to the .NET Framework Class Library](../../standard/class-library-overview.md#system-namespace).</span></span>

## <a name="pinvokelibdll"></a><span data-ttu-id="23369-148">PinvokeLib.dll</span><span class="sxs-lookup"><span data-stu-id="23369-148">PinvokeLib.dll</span></span>

<span data-ttu-id="23369-149">다음 코드에서는 Pinvoke.dll에서 제공되는 라이브러리 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-149">The following code defines the library functions provided by Pinvoke.dll.</span></span> <span data-ttu-id="23369-150">이 섹션에 설명된 대부분 샘플이 이 라이브러리를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="23369-150">Many samples described in this section call this library.</span></span>

### <a name="example"></a><span data-ttu-id="23369-151">예제</span><span class="sxs-lookup"><span data-stu-id="23369-151">Example</span></span>

[!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]

[!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]
