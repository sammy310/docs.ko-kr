---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325245"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a><span data-ttu-id="d2220-101">HttpSys: 클라이언트 인증서 재협상을 기본적으로 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d2220-101">HttpSys: Client certificate renegotiation disabled by default</span></span>

<span data-ttu-id="d2220-102">연결을 재협상하고 클라이언트 인증서를 요청하는 옵션이 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2220-102">The option to renegotiate a connection and request a client certificate has been disabled by default.</span></span> <span data-ttu-id="d2220-103">자세한 내용은 이슈 [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2220-103">For discussion, see issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d2220-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d2220-104">Version introduced</span></span>

<span data-ttu-id="d2220-105">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="d2220-105">ASP.NET Core 5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d2220-106">이전 동작</span><span class="sxs-lookup"><span data-stu-id="d2220-106">Old behavior</span></span>

<span data-ttu-id="d2220-107">연결을 재협상하여 클라이언트 인증서를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2220-107">The connection can be renegotiated to request a client certificate.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d2220-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="d2220-108">New behavior</span></span>

<span data-ttu-id="d2220-109">초기 연결 핸드셰이크 중에만 클라이언트 인증서를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2220-109">Client certificates can only be requested during the initial connection handshake.</span></span> <span data-ttu-id="d2220-110">자세한 내용은 끌어오기 요청 [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2220-110">For more information, see pull request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d2220-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d2220-111">Reason for change</span></span>

<span data-ttu-id="d2220-112">재협상으로 인해 많은 성능 및 교착 상태 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2220-112">Renegotiation caused a number of performance and deadlock issues.</span></span> <span data-ttu-id="d2220-113">또한 재협상은 HTTP/2에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2220-113">It's also not supported in HTTP/2.</span></span> <span data-ttu-id="d2220-114">이 동작을 제어하는 옵션이 ASP.NET Core 3.1에서 도입된 시기의 자세한 상황 정보는 이슈 [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2220-114">For additional context from when the option to control this behavior was introduced in ASP.NET Core 3.1, see issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d2220-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d2220-115">Recommended action</span></span>

<span data-ttu-id="d2220-116">클라이언트 인증서가 필요한 앱은 *netsh.exe*를 사용하여 `clientcertnegotiation` 옵션을 `enabled`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2220-116">Apps that require client certificates should use *netsh.exe* to set the `clientcertnegotiation` option to `enabled`.</span></span> <span data-ttu-id="d2220-117">자세한 내용은 [netsh http 명령](/windows-server/networking/technologies/netsh/netsh-http)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2220-117">For more information, see [netsh http commands](/windows-server/networking/technologies/netsh/netsh-http).</span></span>

<span data-ttu-id="d2220-118">앱의 일부에서만 클라이언트 인증서를 사용하도록 설정하려면 [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates)(선택적 클라이언트 인증서)의 참고 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2220-118">If you want client certificates enabled for only some parts of your app, see the guidance at [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span></span>

<span data-ttu-id="d2220-119">이전 재협상 동작이 필요한 경우 `HttpSysOptions.ClientCertificateMethod`를 이전 값 `ClientCertificateMethod.AllowRenegotiate`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2220-119">If you need the old renegotiate behavior, set `HttpSysOptions.ClientCertificateMethod` to the old value `ClientCertificateMethod.AllowRenegotiate`.</span></span> <span data-ttu-id="d2220-120">위 내용과 연결된 참고 자료에서 설명하는 이유 때문에 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2220-120">This isn't recommended for the reasons outlined above and in the linked guidance.</span></span>

#### <a name="category"></a><span data-ttu-id="d2220-121">범주</span><span class="sxs-lookup"><span data-stu-id="d2220-121">Category</span></span>

<span data-ttu-id="d2220-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2220-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d2220-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d2220-123">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
