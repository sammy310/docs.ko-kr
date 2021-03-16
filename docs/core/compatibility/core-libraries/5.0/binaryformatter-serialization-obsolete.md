---
title: '호환성이 손상되는 변경: ASP.NET 앱에서 BinaryFormatter serialization 메서드가 사용되지 않고 금지됨'
description: BinaryFormatter, Formatter, IFormatter에서 serialize 및 deserialize 메서드가 사용되지 않는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 8c31a95683526ba394101d449b5ae3328f57f3c3
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257663"
---
# <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a><span data-ttu-id="9c249-103">ASP.NET 앱에서 BinaryFormatter serialization 메서드가 사용되지 않고 금지됨</span><span class="sxs-lookup"><span data-stu-id="9c249-103">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>

<span data-ttu-id="9c249-104"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> 및 <xref:System.Runtime.Serialization.IFormatter>에 대한 `Serialize` 및 `Deserialize` 메서드는 이제 경고로 표시되며 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-104">`Serialize` and `Deserialize` methods on <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter>, and <xref:System.Runtime.Serialization.IFormatter> are now obsolete as warning.</span></span> <span data-ttu-id="9c249-105">또한 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization은 ASP.NET 앱에서 기본적으로 금지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-105">Additionally, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is prohibited by default for ASP.NET apps.</span></span>

## <a name="change-description"></a><span data-ttu-id="9c249-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="9c249-106">Change description</span></span>

<span data-ttu-id="9c249-107"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>의 [보안 취약성](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) 때문에 다음 메서드는 이제 사용되지 않으며 `SYSLIB0011` ID를 사용하여 컴파일 시간 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-107">Due to [security vulnerabilities](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following methods are now obsolete and produce a compile-time warning with ID `SYSLIB0011`.</span></span> <span data-ttu-id="9c249-108">또한 ASP.NET Core 5.0 이상 앱에서 웹앱이 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 기능을 다시 사용하도록 설정하지 않는 한 <xref:System.NotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-108">Additionally, in ASP.NET Core 5.0 and later apps, they will throw a <xref:System.NotSupportedException>, unless the web app has re-enabled <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> functionality.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

<span data-ttu-id="9c249-109">다음 serialization 메서드도 더 이상 사용되지 않으며 `SYSLIB0011` 경고를 생성하지만 동작은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-109">The following serialization methods are also obsolete and produce warning `SYSLIB0011`, but have no behavioral changes:</span></span>

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="version-introduced"></a><span data-ttu-id="9c249-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="9c249-110">Version introduced</span></span>

<span data-ttu-id="9c249-111">5.0</span><span class="sxs-lookup"><span data-stu-id="9c249-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="9c249-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="9c249-112">Reason for change</span></span>

<span data-ttu-id="9c249-113">이러한 메서드는 .NET 에코시스템에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 사용을 줄이기 위한 노력의 일환으로 사용되지 않음으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-113">These methods are marked obsolete as part of an effort to wind down usage of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> within the .NET ecosystem.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="9c249-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="9c249-114">Recommended action</span></span>

- <span data-ttu-id="9c249-115">코드에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 사용을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-115">Stop using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in your code.</span></span> <span data-ttu-id="9c249-116">대신, <xref:System.Text.Json.JsonSerializer> 또는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-116">Instead, consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="9c249-117">자세한 내용은 [BinaryFormatter 보안 가이드](../../../../standard/serialization/binaryformatter-security-guide.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c249-117">For more information, see [BinaryFormatter security guide](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

- <span data-ttu-id="9c249-118"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 컴파일 시간 경고 `SYSLIB0011`을 일시적으로 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-118">You can temporarily suppress the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> compile-time warning, which is `SYSLIB0011`.</span></span> <span data-ttu-id="9c249-119">이 옵션을 선택하기 전에 코드에서 위험을 철저히 평가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-119">We recommend that you thoroughly assess your code for risks before choosing this option.</span></span> <span data-ttu-id="9c249-120">경고를 표시하지 않는 가장 쉬운 방법은 개별 호출 사이트를 `#pragma` 지시문으로 묶는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-120">The easiest way to suppress the warnings is to surround the individual call site with `#pragma` directives.</span></span>

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

  <span data-ttu-id="9c249-121">프로젝트 파일에서도 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-121">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  <span data-ttu-id="9c249-122">프로젝트 파일에서 경고를 표시하지 않으면 프로젝트의 모든 코드 파일에서 경고가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-122">If you suppress the warning in the project file, the warning is suppressed for all code files in the project.</span></span> <span data-ttu-id="9c249-123">`SYSLIB0011`을 표시하지 않아도 다른 사용되지 않는 API를 사용하여 발생하는 경고는 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-123">Suppressing `SYSLIB0011` does not suppress warnings caused by using other obsolete APIs.</span></span>

- <span data-ttu-id="9c249-124">ASP.NET 앱에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>를 계속 사용하려면 프로젝트 파일에서 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-124">To continue using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in ASP.NET apps, you can re-enable it in the project file.</span></span> <span data-ttu-id="9c249-125">그러나 이렇게 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9c249-125">However, it's strongly recommended not to do this.</span></span> <span data-ttu-id="9c249-126">자세한 내용은 [BinaryFormatter 보안 가이드](../../../../standard/serialization/binaryformatter-security-guide.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c249-126">For more information, see [BinaryFormatter security guide](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

<span data-ttu-id="9c249-127">권장 작업에 대한 자세한 내용은 [BinaryFormatter 사용 중지 및 비활성화 오류 해결](../../../../standard/serialization/binaryformatter-security-guide.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c249-127">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="9c249-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9c249-128">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET Core

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
