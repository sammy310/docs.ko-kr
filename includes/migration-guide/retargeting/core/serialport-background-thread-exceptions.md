---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614746"
---
### <a name="serialport-background-thread-exceptions"></a><span data-ttu-id="2b7d3-101">SerialPort 백그라운드 스레드 예외</span><span class="sxs-lookup"><span data-stu-id="2b7d3-101">SerialPort background thread exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="2b7d3-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="2b7d3-102">Details</span></span>

<span data-ttu-id="2b7d3-103"><xref:System.IO.Ports.SerialPort> 스트림을 사용하여 만든 백그라운드 스레드는 OS 예외가 throw될 때 더 이상 프로세스를 종료하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-103">Background threads created with <xref:System.IO.Ports.SerialPort> streams no longer terminate the process when OS exceptions are thrown.</span></span> <br/><span data-ttu-id="2b7d3-104">.NET Framework 4.7 및 이전 버전을 대상으로 하는 애플리케이션에서 운영 체제 예외가 <xref:System.IO.Ports.SerialPort> 스트림을 사용하여 만든 백그라운드에서 throw되면 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-104">In applications that target the .NET Framework 4.7 and earlier versions, a process is terminated when an operating system exception is thrown on a background thread created with a <xref:System.IO.Ports.SerialPort> stream.</span></span> <br/><span data-ttu-id="2b7d3-105">.NET Framework 4.7.1 또는 이상 버전을 대상으로 하는 애플리케이션에서 백그라운드 스레드는 활성 직렬 포트와 관련된 OS 이벤트에 대해 기다리며 직렬 포트의 급격한 제거와 같은 일부 경우에 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-105">In applications that target the .NET Framework 4.7.1 or a later version, background threads wait for OS events related to the active serial port and could crash in some cases, such as sudden removal of the serial port.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2b7d3-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="2b7d3-106">Suggestion</span></span>

<span data-ttu-id="2b7d3-107">.NET Framework 4.7.1을 대상으로 하는 앱의 경우, 필요하지 않으면 `app.config` 파일의 `<runtime>` 섹션에 다음을 추가하여 예외 처리를 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-107">For apps that target the .NET Framework 4.7.1, you can opt out of the exception handling if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

<span data-ttu-id="2b7d3-108">이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 앱의 경우 `app.config` 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 예외 처리를 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-108">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.1 or later, you can opt in to the exception handling by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| <span data-ttu-id="2b7d3-109">이름</span><span class="sxs-lookup"><span data-stu-id="2b7d3-109">Name</span></span>    | <span data-ttu-id="2b7d3-110">값</span><span class="sxs-lookup"><span data-stu-id="2b7d3-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2b7d3-111">Scope</span><span class="sxs-lookup"><span data-stu-id="2b7d3-111">Scope</span></span>   | <span data-ttu-id="2b7d3-112">부</span><span class="sxs-lookup"><span data-stu-id="2b7d3-112">Minor</span></span>       |
| <span data-ttu-id="2b7d3-113">버전</span><span class="sxs-lookup"><span data-stu-id="2b7d3-113">Version</span></span> | <span data-ttu-id="2b7d3-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="2b7d3-114">4.7.1</span></span>       |
| <span data-ttu-id="2b7d3-115">형식</span><span class="sxs-lookup"><span data-stu-id="2b7d3-115">Type</span></span>    | <span data-ttu-id="2b7d3-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="2b7d3-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2b7d3-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2b7d3-117">Affected APIs</span></span>

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
