---
title: '호환성이 손상되는 변경: UTF-7 코드 경로가 사용되지 않음'
description: UTF7 및 UTF7Encoding 생성자가 사용되지 않는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 7a0ba771e0fac2908ca37f16afb10118e1537161
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256987"
---
# <a name="utf-7-code-paths-are-obsolete"></a><span data-ttu-id="6baa0-103">UTF-7 코드 경로가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="6baa0-103">UTF-7 code paths are obsolete</span></span>

<span data-ttu-id="6baa0-104">UTF-7 인코딩은 더 이상 애플리케이션에서 광범위하게 사용되지 않으며, 이제 많은 사양에서는 교환에 [사용을 금지](https://security.stackexchange.com/a/68609/3573)합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-104">The UTF-7 encoding is no longer in wide use among applications, and many specs now [forbid its use](https://security.stackexchange.com/a/68609/3573) in interchange.</span></span> <span data-ttu-id="6baa0-105">간혹 UTF-7로 인코딩된 데이터를 기대하지 않는 애플리케이션에서 [공격 벡터로 사용](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7)되기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-105">It's also occasionally [used as an attack vector](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) in applications that don't anticipate encountering UTF-7-encoded data.</span></span> <span data-ttu-id="6baa0-106">오류 검색 기능이 제공되지 않기 때문에 Microsoft는 <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>을 사용하지 않도록 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-106">Microsoft warns against use of <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> because it doesn't provide error detection.</span></span>

<span data-ttu-id="6baa0-107">따라서 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 속성 및 <xref:System.Text.UTF7Encoding.%23ctor%2A> 생성자는 이제 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-107">Consequently, the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property and <xref:System.Text.UTF7Encoding.%23ctor%2A> constructors are now obsolete.</span></span> <span data-ttu-id="6baa0-108">또한 더 이상 <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> 및 <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType>을 사용하여 `UTF-7`을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-108">Additionally, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> and <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> no longer allow you to specify `UTF-7`.</span></span>

## <a name="change-description"></a><span data-ttu-id="6baa0-109">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="6baa0-109">Change description</span></span>

<span data-ttu-id="6baa0-110">이전에는 <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> API를 사용하여 UTF-7 인코딩의 인스턴스를 만들 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-110">Previously, you could create an instance of the UTF-7 encoding by using the <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> APIs.</span></span> <span data-ttu-id="6baa0-111">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="6baa0-111">For example:</span></span>

```csharp
Encoding enc1 = Encoding.GetEncoding("utf-7"); // By name.
Encoding enc2 = Encoding.GetEncoding(65000); // By code page.
```

<span data-ttu-id="6baa0-112">또한 UTF-7 인코딩을 나타내는 인스턴스는 시스템에 등록된 모든 <xref:System.Text.Encoding> 인스턴스를 열거하는 <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> 메서드로 열거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-112">Additionally, an instance that represents the UTF-7 encoding was enumerated by the <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> method, which enumerates all the <xref:System.Text.Encoding> instances registered on the system.</span></span>

<span data-ttu-id="6baa0-113">.NET 5부터 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 속성 및 <xref:System.Text.UTF7Encoding.%23ctor%2A> 생성자는 사용되지 않으며 경고 `SYSLIB0001`(또는 미리 보기 버전의 `MSLIB0001`)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-113">Starting in .NET 5, the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property and <xref:System.Text.UTF7Encoding.%23ctor%2A> constructors are obsolete and produce warning `SYSLIB0001` (or `MSLIB0001` in preview versions).</span></span> <span data-ttu-id="6baa0-114">그러나 <xref:System.Text.UTF7Encoding> 클래스를 사용할 때 호출자가 수신하는 경고 수를 줄이기 위해 <xref:System.Text.UTF7Encoding> 형식 자체는 사용되지 않음으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-114">However, to reduce the number of warnings that callers receive when using the <xref:System.Text.UTF7Encoding> class, the <xref:System.Text.UTF7Encoding> type itself is not marked obsolete.</span></span>

```csharp
// The next line generates warning SYSLIB0001.
UTF7Encoding enc = new UTF7Encoding();
// The next line does not generate a warning.
byte[] bytes = enc.GetBytes("Hello world!");
```

<span data-ttu-id="6baa0-115">또한 <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> 메서드는 인코딩 이름 `utf-7` 및 코드 페이지 `65000`을 `unknown`으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-115">Additionally, the <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> methods treat the encoding name `utf-7` and the code page `65000` as `unknown`.</span></span> <span data-ttu-id="6baa0-116">인코딩을 `unknown`으로 처리하면 메서드가 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-116">Treating the encoding as `unknown` causes the method to throw an <xref:System.ArgumentException>.</span></span>

```csharp
// Throws ArgumentException, same as calling Encoding.GetEncoding("unknown").
Encoding enc = Encoding.GetEncoding("utf-7");
```

<span data-ttu-id="6baa0-117">마지막으로, <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> 메서드는 반환하는 <xref:System.Text.EncodingInfo> 배열에 UTF-7 인코딩을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-117">Finally, the <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> method doesn't include the UTF-7 encoding in the <xref:System.Text.EncodingInfo> array that it returns.</span></span> <span data-ttu-id="6baa0-118">이 인코딩은 인스턴스화할 수 없기 때문에 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-118">The encoding is excluded because it cannot be instantiated.</span></span>

```csharp
foreach (EncodingInfo encInfo in Encoding.GetEncodings())
{
    // The next line would throw if GetEncodings included UTF-7.
    Encoding enc = Encoding.GetEncoding(encInfo.Name);
}
```

## <a name="reason-for-change"></a><span data-ttu-id="6baa0-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6baa0-119">Reason for change</span></span>

<span data-ttu-id="6baa0-120">많은 애플리케이션이 신뢰할 수 없는 소스에서 제공하는 인코딩 이름 값을 사용하여 `Encoding.GetEncoding("encoding-name")`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-120">Many applications call `Encoding.GetEncoding("encoding-name")` with an encoding name value that's provided by an untrusted source.</span></span> <span data-ttu-id="6baa0-121">예를 들어 웹 클라이언트 또는 서버가 `Content-Type` 헤더의 `charset` 부분을 가져와서 유효성을 검사하지 않고 `Encoding.GetEncoding`에 직접 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-121">For example, a web client or server might take the `charset` portion of the `Content-Type` header and pass the value directly to `Encoding.GetEncoding` without validating it.</span></span> <span data-ttu-id="6baa0-122">이렇게 하면 악의적인 엔드포인트에서 `Content-Type: ...; charset=utf-7`을 지정할 수 있으므로 수신하는 애플리케이션이 잘못 동작하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-122">This could allow a malicious endpoint to specify `Content-Type: ...; charset=utf-7`, which could cause the receiving application to misbehave.</span></span>

<span data-ttu-id="6baa0-123">또한 UTF-7 코드 경로를 사용하지 않도록 설정하면 Blazor에서 사용하는 것과 같이 컴파일러를 최적화하여 결과 애플리케이션에서 이러한 코드 경로를 완전히 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-123">Additionally, disabling UTF-7 code paths allows optimizing compilers, such as those used by Blazor, to remove these code paths entirely from the resulting application.</span></span> <span data-ttu-id="6baa0-124">결과적으로 컴파일된 애플리케이션이 더 효율적으로 실행되고 차지하는 디스크 공간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-124">As a result, the compiled applications run more efficiently and take less disk space.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6baa0-125">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6baa0-125">Version introduced</span></span>

<span data-ttu-id="6baa0-126">5.0</span><span class="sxs-lookup"><span data-stu-id="6baa0-126">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6baa0-127">권장 조치</span><span class="sxs-lookup"><span data-stu-id="6baa0-127">Recommended action</span></span>

<span data-ttu-id="6baa0-128">대부분의 경우 아무 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-128">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="6baa0-129">그러나 이전에 UTF-7 관련 코드 경로가 활성화된 앱의 경우 다음 지침을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="6baa0-129">However, for apps that have previously activated UTF-7-related code paths, consider the guidance that follows.</span></span>

- <span data-ttu-id="6baa0-130">앱이 신뢰할 수 없는 소스에서 제공하는 알 수 없는 인코딩 이름을 가진 <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>을 호출하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6baa0-130">If your app calls <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> with unknown encoding names provided by an untrusted source:</span></span>

  <span data-ttu-id="6baa0-131">대신, 인코딩 이름을 구성 가능한 허용 목록과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-131">Instead, compare the encoding names against a configurable allow list.</span></span> <span data-ttu-id="6baa0-132">구성 가능한 허용 목록은 최소한 산업 표준 "utf-8"을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-132">The configurable allow list should at minimum include the industry-standard "utf-8".</span></span> <span data-ttu-id="6baa0-133">클라이언트 및 규정 요구 사항에 따라 "GB18030"과 같은 지역 특정 인코딩을 허용해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-133">Depending on your clients and regulatory requirements, you may also need to allow region-specific encodings, such as "GB18030".</span></span>

  <span data-ttu-id="6baa0-134">허용 목록을 구현하지 않으면 <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>은 시스템에 기본 제공되거나 사용자 지정 <xref:System.Text.EncodingProvider>를 통해 등록된 모든 <xref:System.Text.Encoding>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-134">If you don't implement an allow list, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> will return any <xref:System.Text.Encoding> that's built into the system or that's registered via a custom <xref:System.Text.EncodingProvider>.</span></span> <span data-ttu-id="6baa0-135">서비스 요구 사항을 감사하여 원하는 동작인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-135">Audit your service's requirements to validate that this is the desired behavior.</span></span> <span data-ttu-id="6baa0-136">애플리케이션이 이 문서의 뒷부분에서 설명하는 호환성 스위치를 다시 사용하도록 설정하지 않는 한 기본적으로 UTF-7은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-136">UTF-7 continues to be disabled by default unless your application re-enables the compatibility switch mentioned later in this article.</span></span>

- <span data-ttu-id="6baa0-137">사용자 고유의 프로토콜 또는 파일 형식에서 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 또는 <xref:System.Text.UTF7Encoding>을 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6baa0-137">If you're using <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding> within your own protocol or file format:</span></span>

  <span data-ttu-id="6baa0-138"><xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> 또는 <xref:System.Text.UTF8Encoding>을 사용하도록 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-138">Switch to using <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> or <xref:System.Text.UTF8Encoding>.</span></span> <span data-ttu-id="6baa0-139">UTF-8은 업계 표준이며 광범위한 언어, 운영 체제 및 런타임에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-139">UTF-8 is an industry standard and is widely supported across languages, operating systems, and runtimes.</span></span> <span data-ttu-id="6baa0-140">UTF-8을 사용하면 나중에 코드를 더 쉽게 유지 관리할 수 있으며, 나머지 에코시스템과 상호 운용이 더 간단해집니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-140">Using UTF-8 eases future maintenance of your code and makes it more interoperable with the rest of the ecosystem.</span></span>

- <span data-ttu-id="6baa0-141"><xref:System.Text.Encoding> 인스턴스를 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>과 비교하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6baa0-141">If you're comparing an <xref:System.Text.Encoding> instance against <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span></span>

  <span data-ttu-id="6baa0-142">대신, 잘 알려진 UTF-7 코드 페이지 `65000`에 대해 검사를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-142">Instead, consider performing a check against the well-known UTF-7 code page, which is `65000`.</span></span> <span data-ttu-id="6baa0-143">이 코드 페이지와 비교하여 경고를 방지하고, 다른 사용자가 `new UTF7Encoding()`를 호출했거나 형식이 서브클래싱된 경우와 같은 일부 특수한 사례를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-143">By comparing against the code page, you avoid the warning and also handle some edge cases, such as if somebody called `new UTF7Encoding()` or subclassed the type.</span></span>

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

- <span data-ttu-id="6baa0-144"><xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 또는 <xref:System.Text.UTF7Encoding>을 사용해야 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6baa0-144">If you must use <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding>:</span></span>

  <span data-ttu-id="6baa0-145">코드에서 또는 프로젝트의 *.csproj* 파일 내에서 `SYSLIB0001` 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-145">You can suppress the `SYSLIB0001` warning in code or within your project's *.csproj* file.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0001 // Disable the warning.
  Encoding enc = Encoding.UTF7;
  #pragma warning restore SYSLIB0001 // Re-enable the warning.
  ```

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > <span data-ttu-id="6baa0-146">`SYSLIB0001`을 표시하지 않으면 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 및 <xref:System.Text.UTF7Encoding> 사용 중지 경고도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-146">Suppressing `SYSLIB0001` only disables the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> and <xref:System.Text.UTF7Encoding> obsoletion warnings.</span></span> <span data-ttu-id="6baa0-147">다른 경고를 사용하지 않도록 설정하거나 <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>와 같은 API의 동작을 변경하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-147">It doesn't disable any other warnings or change the behavior of APIs like <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="6baa0-148">`Encoding.GetEncoding("utf-7", ...)`을 지원해야 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6baa0-148">If you must support `Encoding.GetEncoding("utf-7", ...)`:</span></span>

  <span data-ttu-id="6baa0-149">호환성 스위치를 통해 이에 대한 지원을 다시 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-149">You can re-enable support for this via a compatibility switch.</span></span> <span data-ttu-id="6baa0-150">다음 예제와 같이 애플리케이션의 *.csproj* 파일 또는 [런타임 구성 파일](../../../run-time-config/index.md)에서 이 호환성 스위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-150">This compatibility switch can be specified in the application's *.csproj* file or in a [run-time configuration file](../../../run-time-config/index.md), as shown in the following examples.</span></span>

  <span data-ttu-id="6baa0-151">애플리케이션의 *.csproj* 파일:</span><span class="sxs-lookup"><span data-stu-id="6baa0-151">In the application's *.csproj* file:</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- Re-enable support for UTF-7 -->
     <EnableUnsafeUTF7Encoding>true</EnableUnsafeUTF7Encoding>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="6baa0-152">애플리케이션의 *runtimeconfig.template.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="6baa0-152">In the application's *runtimeconfig.template.json* file:</span></span>

  ```json
  {
    "configProperties": {
      "System.Text.Encoding.EnableUnsafeUTF7Encoding": true
    }
  }
  ```

  > [!TIP]
  > <span data-ttu-id="6baa0-153">UTF-7에 대한 지원을 다시 활성화하는 경우 <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>을 호출하는 코드의 보안 검토를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6baa0-153">If you re-enable support for UTF-7, you should perform a security review of code that calls <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6baa0-154">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6baa0-154">Affected APIs</span></span>

- <xref:System.Text.Encoding.UTF7?displayProperty=fullName>
- <xref:System.Text.UTF7Encoding.%23ctor>
- <xref:System.Text.UTF7Encoding.%23ctor(System.Boolean)>
- <xref:System.Text.Encoding.GetEncoding(System.Int32)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncodings?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `System.Text.Encoding.UTF7`
- `System.Text.UTF7Encoding.#ctor`
- `System.Text.UTF7Encoding.#ctor(System.Boolean)`
- `System.Text.Encoding.GetEncoding(System.Int32)`
- `System.Text.Encoding.GetEncoding(System.String)`
- `System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncodings`

-->
