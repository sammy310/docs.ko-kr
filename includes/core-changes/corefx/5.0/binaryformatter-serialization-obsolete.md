---
ms.openlocfilehash: c5204e8c80cb737338b053c39083c0cc43786447
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517332"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a><span data-ttu-id="d1950-101">ASP.NET 앱에서 BinaryFormatter serialization 메서드가 사용되지 않고 금지됨</span><span class="sxs-lookup"><span data-stu-id="d1950-101">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>

<span data-ttu-id="d1950-102"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> 및 <xref:System.Runtime.Serialization.IFormatter>에 대한 `Serialize` 및 `Deserialize` 메서드는 이제 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-102">`Serialize` and `Deserialize` methods on <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter>, and <xref:System.Runtime.Serialization.IFormatter> are now obsolete.</span></span> <span data-ttu-id="d1950-103">또한 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization은 ASP.NET 앱에서 기본적으로 금지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-103">Additionally, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is prohibited by default for ASP.NET apps.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d1950-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d1950-104">Change description</span></span>

<span data-ttu-id="d1950-105"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>의 [보안 취약성](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) 때문에 다음 메서드는 이제 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-105">Due to [security vulnerabilities](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following methods are now obsolete.</span></span> <span data-ttu-id="d1950-106">또한 ASP.NET 5.0 이상 앱에서 웹앱이 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 기능을 다시 사용하도록 설정하지 않는 한 <xref:System.NotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-106">Additionally, in ASP.NET 5.0 and later apps, they will throw a <xref:System.NotSupportedException>, unless the web app has re-enabled <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> functionality.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

<span data-ttu-id="d1950-107">이러한 메서드는 .NET 에코시스템에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 사용을 줄이기 위한 노력의 일환으로 사용되지 않음으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-107">These methods are marked obsolete as part of an effort to wind down usage of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> within the .NET ecosystem.</span></span>

<span data-ttu-id="d1950-108">다음 serialization 메서드도 더 이상 사용되지 않지만 동작은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-108">The following serialization methods are also now obsolete, but have no behavioral changes:</span></span>

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a><span data-ttu-id="d1950-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1950-109">Version introduced</span></span>

<span data-ttu-id="d1950-110">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="d1950-110">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d1950-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d1950-111">Recommended action</span></span>

- <span data-ttu-id="d1950-112">코드에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 사용을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-112">Stop using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in your code.</span></span> <span data-ttu-id="d1950-113">대신, <xref:System.Text.Json.JsonSerializer> 또는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-113">Instead, consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="d1950-114">자세한 내용은 [BinaryFormatter 보안 가이드](../../../../docs/standard/serialization/binaryformatter-security-guide.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1950-114">For more information, see [BinaryFormatter security guide](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span></span>

- <span data-ttu-id="d1950-115"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 컴파일 시간 경고 `SYSLIB0011`을 일시적으로 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-115">You can temporarily suppress the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> compile-time warning, which is `SYSLIB0011`.</span></span> <span data-ttu-id="d1950-116">이 옵션을 선택하기 전에 코드에서 위험을 철저히 평가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-116">We recommend that you thoroughly assess your code for risks before choosing this option.</span></span> <span data-ttu-id="d1950-117">경고를 표시하지 않는 가장 쉬운 방법은 개별 호출 사이트를 `#pragma` 지시문으로 묶는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-117">The easiest way to suppress the warnings is to surround the individual call site with `#pragma` directives.</span></span>

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  <span data-ttu-id="d1950-118">프로젝트 파일에서도 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-118">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  <span data-ttu-id="d1950-119">프로젝트 파일에서 경고를 표시하지 않으면 프로젝트의 모든 코드 파일에서 경고가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-119">If you suppress the warning in the project file, the warning is suppressed for all code files in the project.</span></span> <span data-ttu-id="d1950-120">SYSLIB0011을 표시하지 않아도 다른 사용되지 않는 API를 사용하여 발생하는 경고는 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-120">Suppressing SYSLIB0011 does not suppress warnings caused by using other obsolete APIs.</span></span>

- <span data-ttu-id="d1950-121">ASP.NET 앱에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>를 계속 사용하려면 프로젝트 파일에서 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-121">To continue using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in ASP.NET apps, you can re-enable it in the project file.</span></span> <span data-ttu-id="d1950-122">그러나 이렇게 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1950-122">However, it's strongly recommended not to do this.</span></span> <span data-ttu-id="d1950-123">자세한 내용은 [BinaryFormatter 보안 가이드](../../../../docs/standard/serialization/binaryformatter-security-guide.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1950-123">For more information, see [BinaryFormatter security guide](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span></span>

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

<span data-ttu-id="d1950-124">권장 작업에 대한 자세한 내용은 [BinaryFormatter 사용 중지 및 비활성화 오류 해결](https://aka.ms/binaryformatter)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1950-124">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

#### <a name="category"></a><span data-ttu-id="d1950-125">범주</span><span class="sxs-lookup"><span data-stu-id="d1950-125">Category</span></span>

- <span data-ttu-id="d1950-126">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="d1950-126">Core .NET libraries</span></span>
- <span data-ttu-id="d1950-127">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d1950-127">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d1950-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d1950-128">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
