---
ms.openlocfilehash: 8693c1fdef5fa194b16127d4f1dd87e23ad68f2d
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438043"
---
### <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a><span data-ttu-id="83795-101">RCW를 `InterfaceIsIInspectable` 인터페이스로 캐스팅하면 PlatformNotSupportedException이 throw됨</span><span class="sxs-lookup"><span data-stu-id="83795-101">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>

<span data-ttu-id="83795-102"><xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>로 표시된 인터페이스로 RCW(런타임 호출 가능 래퍼)를 캐스팅하면 이제 <xref:System.PlatformNotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="83795-102">Casting a runtime callable wrapper (RCW) to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> now throws a <xref:System.PlatformNotSupportedException>.</span></span> <span data-ttu-id="83795-103">이 변경 내용은 [.NET에서 WinRT 지원 제거](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net)에 따른 후속 조치입니다.</span><span class="sxs-lookup"><span data-stu-id="83795-103">This change is a follow up to the [removal of WinRT support from .NET](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="83795-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="83795-104">Version introduced</span></span>

<span data-ttu-id="83795-105">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="83795-105">5.0 RC2</span></span>

#### <a name="change-description"></a><span data-ttu-id="83795-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="83795-106">Change description</span></span>

<span data-ttu-id="83795-107">.NET 5.0 미리 보기 6 이전의 .NET 버전에서는 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>로 표시된 인터페이스로 RCW를 캐스팅하는 기능이 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="83795-107">In .NET versions prior to .NET 5.0 preview 6, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> works as expected.</span></span> <span data-ttu-id="83795-108">.NET 5.0 미리 보기 6~8 및 RC1에서는 RCW를 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 인터페이스로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83795-108">In .NET 5.0 previews 6-8 and RC1, you can successfully cast an RCW to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface.</span></span> <span data-ttu-id="83795-109">그러나 런타임에서의 기본 지원이 [.NET 5.0 미리 보기 6에서 제거](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net)되었으므로 인터페이스에서 메서드를 실행하면 액세스를 위반할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83795-109">However, you might get access violations when you execute methods on the interface, because the underlying support in the runtime [was removed in .NET 5.0 preview 6](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span>

<span data-ttu-id="83795-110">.NET 5.0 RC2 이상 버전에서 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>로 표시된 인터페이스로 RCW를 캐스팅하면 캐스트 시간에 <xref:System.PlatformNotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="83795-110">In .NET 5.0 RC2 and later versions, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> throws a <xref:System.PlatformNotSupportedException> at cast time.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="83795-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="83795-111">Reason for change</span></span>

<span data-ttu-id="83795-112"><xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 지원은 [이전 .NET 5.0 미리 보기에서 제거](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net)되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83795-112">The support for <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> was [removed in a previous .NET 5.0 preview](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).</span></span> <span data-ttu-id="83795-113">그러나 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 인터페이스로의 캐스팅은 실수로 간과되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83795-113">However, casting to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface was accidentally overlooked.</span></span> <span data-ttu-id="83795-114">런타임에서 기본 지원이 더 이상 존재하지 않으므로 <xref:System.PlatformNotSupportedException>을 throw하여 정상적인 실패 경로를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="83795-114">Since the underlying support in the runtime no longer exists, throwing a <xref:System.PlatformNotSupportedException> enables a graceful failure path.</span></span> <span data-ttu-id="83795-115">또한 예외를 throw하여 기능이 더 이상 지원되지 않음을 더 쉽게 검색할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="83795-115">Throwing an exception also makes it more discoverable that this feature is no longer supported.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="83795-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="83795-116">Recommended action</span></span>

- <span data-ttu-id="83795-117">Windows 런타임 메타데이터(WinMD) 파일에서 인터페이스를 정의할 수 있는 경우에는 C#/WinRT 도구를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83795-117">If you can define the interface in a Windows runtime metadata (WinMD) file, use the C#/WinRT tool instead.</span></span>

- <span data-ttu-id="83795-118">그렇지 않은 경우에는 인터페이스를 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 대신 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown>으로 표시하고, <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 메서드의 인터페이스 시작 부분에 더미 항목 3개를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83795-118">Otherwise, mark the interface as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> instead of <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, and add three dummy entries to the start of the interface for the <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> methods.</span></span> <span data-ttu-id="83795-119">다음 코드 조각은 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83795-119">The following code snippet shows an example.</span></span>

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

#### <a name="category"></a><span data-ttu-id="83795-120">범주</span><span class="sxs-lookup"><span data-stu-id="83795-120">Category</span></span>

<span data-ttu-id="83795-121">Interop</span><span class="sxs-lookup"><span data-stu-id="83795-121">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="83795-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="83795-122">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

-->
