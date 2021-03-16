---
title: '호환성이 손상되는 변경: 암호화 추상화의 기본 구현 인스턴스화는 지원되지 않습니다.'
description: 암호화 추상화에 대한 매개 변수가 없는 Create() 오버로드가 사용되지 않는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/16/2020
ms.openlocfilehash: b75f3568317d1db8ae1bb629f760aaec7e69776a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256792"
---
# <a name="instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported"></a><span data-ttu-id="f71e8-103">암호화 추상화의 기본 구현 인스턴스화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-103">Instantiating default implementations of cryptographic abstractions is not supported</span></span>

<span data-ttu-id="f71e8-104">암호화 추상화에 대한 매개 변수가 없는 `Create()` 오버로드는 .NET 5.0부터 경고로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-104">The parameterless `Create()` overloads on cryptographic abstractions are obsolete as warning as of .NET 5.0.</span></span>

## <a name="change-description"></a><span data-ttu-id="f71e8-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f71e8-105">Change description</span></span>

<span data-ttu-id="f71e8-106">.NET Framework 2.0 - 4.8에서 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>과 같은 추상 암호화 기본 팩터리는 다른 알고리즘을 반환하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-106">In .NET Framework 2.0 - 4.8, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> can be configured to return different algorithms.</span></span> <span data-ttu-id="f71e8-107">예를 들어 .NET Framework 4.8의 기본 설치에서 매개 변수가 없는 정적 메서드 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>은 다음 코드 조각과 같이 SHA1 알고리즘의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-107">For example, on a default install of .NET Framework 4.8, the parameterless, static method <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> returns an instance of the SHA1 algorithm, as shown in the following snippet.</span></span>

<span data-ttu-id="f71e8-108">**.NET Framework만 해당**</span><span class="sxs-lookup"><span data-stu-id="f71e8-108">**.NET Framework only**</span></span>

```csharp
// Return an instance of the default hash algorithm (SHA1).
HashAlgorithm alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA1CryptoServiceProvider'.
Console.WriteLine(alg.GetType());

// Change the default algorithm to be SHA256, not SHA1.
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), typeof(HashAlgorithm).FullName);
alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA256CryptoServiceProvider'.
Console.WriteLine(alg.GetType());
```

<span data-ttu-id="f71e8-109">프로그래밍 방식으로 `CryptoConfig`를 호출할 필요 없이 [머신 전체 구성](../../../../framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)을 사용하여 기본 알고리즘을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-109">You can also use [machine-wide configuration](../../../../framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) to change the default algorithm without needing to call into `CryptoConfig` programmatically.</span></span>

<span data-ttu-id="f71e8-110">.NET Core 2.0 - 3.1에서 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>과 같은 추상 암호화 기본 팩터리는 항상 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-110">In .NET Core 2.0 - 3.1, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> always throw a <xref:System.PlatformNotSupportedException>.</span></span>

```csharp
// Throws PlatformNotSupportedException on .NET Core.
HashAlgorithm alg = HashAlgorithm.Create();
```

<span data-ttu-id="f71e8-111">.NET 5 이상 버전에서 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>과 같은 추상 암호화 기본 팩터리는 사용되지 않는 것으로 표시되고 ID `SYSLIB0007`을 사용하여 컴파일 시간 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-111">In .NET 5 and later versions, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> are marked obsolete and produce a compile-time warning with ID `SYSLIB0007`.</span></span> <span data-ttu-id="f71e8-112">런타임 시 이러한 메서드는 <xref:System.PlatformNotSupportedException>을 계속 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-112">At run time, these methods continue to throw a <xref:System.PlatformNotSupportedException>.</span></span>

```csharp
// Throws PlatformNotSupportedException.
// Also produces compile-time warning SYSLIB0007 on .NET 5+.
HashAlgorithm alg = HashAlgorithm.Create();
```

<span data-ttu-id="f71e8-113">이는 컴파일 시간 전용 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-113">This is a compile-time only change.</span></span> <span data-ttu-id="f71e8-114">.NET Core의 이전 버전에서 런타임 변경은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-114">There is no run-time change from previous versions of .NET Core.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f71e8-115">`Create()` 메서드의 매개 변수가 없는 오버로드만 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-115">Only the parameterless overloads of the `Create()` methods are obsolete.</span></span> <span data-ttu-id="f71e8-116">매개 변수가 있는 오버로드는 더 이상 사용되지 않으며 예상대로 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-116">Parameterized overloads are not obsolete and still function as expected.</span></span>
>
>   ```csharp
>   // Call Create(string), providing an explicit algorithm family name.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   HashAlgorithm hashAlg = HashAlgorithm.Create("SHA256");
>   ```
>
> - <span data-ttu-id="f71e8-117">*특정* 알고리즘 패밀리(추상화 아님)의 매개 변수가 없는 오버로드는 더 이상 사용되지 않으며 예상대로 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-117">Parameterless overloads of *specific* algorithm families (not abstractions) are not obsolete, and will continue to function as expected.</span></span>
>
>   ```csharp
>   // Call a specific algorithm family's parameterless Create() ctor.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   Aes aesAlg = Aes.Create();
>   ```

## <a name="reason-for-change"></a><span data-ttu-id="f71e8-118">변경 이유</span><span class="sxs-lookup"><span data-stu-id="f71e8-118">Reason for change</span></span>

<span data-ttu-id="f71e8-119">레거시 시스템이 적절한 암호화 민첩성을 허용하지 않기 때문에 .NET Framework에 있는 암호화 구성 시스템은 더 이상 .NET Core 및 .NET 5.0+에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-119">The cryptographic configuration system present in .NET Framework is no longer present in .NET Core and .NET 5.0+, since that legacy system doesn't allow for proper cryptographic agility.</span></span> <span data-ttu-id="f71e8-120">.NET의 이전 버전과의 호환성 요구 사항은 또한 프레임워크가 암호화의 발전을 따라 잡기 위해 특정 암호화 API를 업데이트하는 것을 금지합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-120">.NET's backward-compatibility requirements also prohibit the framework from updating certain cryptographic APIs to keep up with advances in cryptography.</span></span> <span data-ttu-id="f71e8-121">예를 들어, <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> 메서드는 SHA-1 해시 알고리즘이 최첨단이었을 때 .NET Framework 1.0에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-121">For example, the <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> method was introduced in .NET Framework 1.0, when the SHA-1 hash algorithm was state-of-the-art.</span></span> <span data-ttu-id="f71e8-122">그 후 20년이 지났고 이제 SHA-1이 중단된 것으로 간주되지만 다른 알고리즘을 반환하도록 <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType>을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-122">Twenty years have passed, and now SHA-1 is considered broken, but we cannot change <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> to return a different algorithm.</span></span> <span data-ttu-id="f71e8-123">그렇게 하면 사용하는 애플리케이션에 허용할 수 없는 주요 변경 사항이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-123">Doing so would introduce an unacceptable breaking change in consuming applications.</span></span>

<span data-ttu-id="f71e8-124">모범 사례에 따르면 암호화 기본 요소(예: AES, SHA-\* 및 RSA)를 사용하는 라이브러리는 이러한 기본 요소를 사용하는 방법을 완전히 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-124">Best practice dictates that libraries that consume cryptographic primitives (such as AES, SHA-\*, and RSA) should be in full control over how they consume these primitives.</span></span> <span data-ttu-id="f71e8-125">미래를 대비해야 하는 애플리케이션은 이러한 기본 요소를 래핑하고 키 관리 및 암호화 민첩성 기능을 추가하는 상위 레벨 라이브러리를 활용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-125">Applications that require future-proofing should utilize higher-level libraries that wrap these primitives and add key management and cryptographic agility capabilities.</span></span> <span data-ttu-id="f71e8-126">이러한 라이브러리는 종종 호스팅 환경에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-126">These libraries are often provided by the hosting environment.</span></span> <span data-ttu-id="f71e8-127">한 가지 예는 호출 애플리케이션을 대신하여 이러한 문제를 처리하는 [ASP.NET의 데이터 보호 라이브러리](/aspnet/core/security/data-protection/)입니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-127">One example is [ASP.NET's Data Protection library](/aspnet/core/security/data-protection/), which handles these concerns on behalf of the calling application.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f71e8-128">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f71e8-128">Version introduced</span></span>

<span data-ttu-id="f71e8-129">5.0</span><span class="sxs-lookup"><span data-stu-id="f71e8-129">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f71e8-130">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f71e8-130">Recommended action</span></span>

- <span data-ttu-id="f71e8-131">권장되는 조치 과정은 현재 사용되지 않는 API에 대한 호출을 특정 알고리즘(예: <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>)에 대한 팩터리 메소드 호출로 대체하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-131">The recommended course of action is to replace calls to the now-obsolete APIs with calls to factory methods for specific algorithms, for example, <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f71e8-132">이렇게 하면 인스턴스화되는 알고리즘을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-132">This gives you full control over which algorithms are instantiated.</span></span>

- <span data-ttu-id="f71e8-133">현재 사용되지 않는 API를 사용하는 .NET Framework 앱에서 생성된 기존 페이로드와의 호환성을 유지해야 하는 경우 다음 표에 제안된 대체 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-133">If you need to maintain compatibility with existing payloads generated by .NET Framework apps that use the now-obsolete APIs, use the replacements suggested in the following table.</span></span> <span data-ttu-id="f71e8-134">표는 .NET Framework 기본 알고리즘에서 해당 .NET 5+까지의 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-134">The table provides a mapping from .NET Framework default algorithms to their .NET 5+ equivalents.</span></span>

  | <span data-ttu-id="f71e8-135">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="f71e8-135">.NET Framework</span></span> | <span data-ttu-id="f71e8-136">.NET Core/.NET 5.0+ 호환 대체 항목</span><span class="sxs-lookup"><span data-stu-id="f71e8-136">.NET Core / .NET 5.0+ compatible replacement</span></span> | <span data-ttu-id="f71e8-137">설명</span><span class="sxs-lookup"><span data-stu-id="f71e8-137">Remarks</span></span> |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | <span data-ttu-id="f71e8-138">SHA-1 알고리즘은 중단된 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-138">The SHA-1 algorithm is considered broken.</span></span> <span data-ttu-id="f71e8-139">가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-139">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="f71e8-140">자세한 지침은 보안 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="f71e8-140">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | <span data-ttu-id="f71e8-141">대부분의 최신 애플리케이션에서는 HMACSHA1 알고리즘이 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-141">The HMACSHA1 algorithm is discouraged for most modern applications.</span></span> <span data-ttu-id="f71e8-142">가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-142">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="f71e8-143">자세한 지침은 보안 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="f71e8-143">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | <span data-ttu-id="f71e8-144">대부분의 최신 애플리케이션에서는 HMACSHA1 알고리즘이 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-144">The HMACSHA1 algorithm is discouraged for most modern applications.</span></span> <span data-ttu-id="f71e8-145">가능하면 더 강력한 알고리즘을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-145">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="f71e8-146">자세한 지침은 보안 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="f71e8-146">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

- <span data-ttu-id="f71e8-147">더 이상 사용되지 않는 매개 변수가 없는 `Create()` 오버로드를 계속 호출해야 하는 경우 코드에서 `SYSLIB0007` 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-147">If you must continue to call the obsolete parameterless `Create()` overloads, you can suppress the `SYSLIB0007` warning in code.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0007 // Disable the warning.
  HashAlgorithm alg = HashAlgorithm.Create(); // Still throws PNSE.
  #pragma warning restore SYSLIB0007 // Re-enable the warning.
  ```

  <span data-ttu-id="f71e8-148">프로젝트 파일에서 경고를 표시하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-148">You can also suppress the warning in your project file.</span></span> <span data-ttu-id="f71e8-149">이렇게 하면 프로젝트 내의 모든 소스 파일에 대한 경고를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-149">Doing so disables the warning for all source files within the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0007 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0007</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > <span data-ttu-id="f71e8-150">`SYSLIB0007`을 표시하지 않으면 여기에 나열된 암호화 API에 대한 삭제 경고만 사용하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-150">Suppressing `SYSLIB0007` disables only the obsoletion warnings for the cryptography APIs listed here.</span></span> <span data-ttu-id="f71e8-151">다른 경고를 사용하지 않도록 설정하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-151">It does not disable any other warnings.</span></span> <span data-ttu-id="f71e8-152">또한 경고를 표시하지 않더라도 사용되지 않는 API는 런타임 시 <xref:System.PlatformNotSupportedException>을 계속 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f71e8-152">Additionally, even if you suppress the warning, these obsoleted APIs will still throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f71e8-153">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f71e8-153">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.AsymmetricAlgorithm.Create`
- `M:System.Security.Cryptography.HashAlgorithm.Create`
- `M:System.Security.Cryptography.HMAC.Create`
- `M:System.Security.Cryptography.KeyedHashAlgorithm.Create`
- `M:System.Security.Cryptography.SymmetricAlgorithm.Create`

### Category

- Cryptography

-->
