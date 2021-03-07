---
title: 4Apr 비밀 빌딩 블록
description: 비밀 구성 요소에 대 한 설명, 해당 기능, 이점 및 적용 방법
author: edwinvw
ms.date: 02/07/2021
ms.openlocfilehash: 94942b396af947b2a3e49b918b2b082c15f4bb08
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401850"
---
# <a name="the-dapr-secrets-building-block"></a><span data-ttu-id="b8df5-103">4Apr 비밀 빌딩 블록</span><span class="sxs-lookup"><span data-stu-id="b8df5-103">The Dapr secrets building block</span></span>

<span data-ttu-id="b8df5-104">엔터프라이즈 응용 프로그램에는 암호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-104">Enterprise applications require secrets.</span></span> <span data-ttu-id="b8df5-105">일반적인 예제는 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-105">Common examples include:</span></span>

- <span data-ttu-id="b8df5-106">사용자 이름 및 암호를 포함 하는 데이터베이스 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-106">A database connection string that contains a username and password.</span></span>
- <span data-ttu-id="b8df5-107">외부 web API를 호출 하는 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-107">An API key for calling an external web API.</span></span>
- <span data-ttu-id="b8df5-108">외부 시스템을 인증 하기 위한 클라이언트 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-108">A client certificate for authenticating to an external system.</span></span>

<span data-ttu-id="b8df5-109">암호는 응용 프로그램 외부에 공개 되지 않도록 신중 하 게 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-109">Secrets must be carefully managed so that they're never disclosed outside of the application.</span></span>

<span data-ttu-id="b8df5-110">오래 전에는 응용 프로그램 코드 베이스 내의 구성 파일에 응용 프로그램 암호를 저장 하는 것이 일반적 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-110">Not long ago, it was popular to store application secrets in a configuration file inside the application codebase.</span></span> <span data-ttu-id="b8df5-111">.NET 개발자는 *web.config* 파일을 fondly 회수할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-111">.NET developers will fondly recall the *web.config* file.</span></span> <span data-ttu-id="b8df5-112">간단 하 게 구현 하는 동안 코드와 함께 비밀을 통합 하는 것은 안전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-112">While simple to implement, integrating secrets to along with code was far from secure.</span></span> <span data-ttu-id="b8df5-113">일반적인 잘못 된 단계는 공용 GIT 리포지토리로 푸시 될 때 파일을 포함 하 여 전 세계에 암호를 노출 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-113">A common misstep was to include the file when pushing to a public GIT repository, exposing the secrets to the world.</span></span>

<span data-ttu-id="b8df5-114">최신 배포 응용 프로그램을 구성 하는 데 널리 승인 된 방법은 [Twelve-Factor 앱](https://12factor.net/)입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-114">A widely accepted methodology for constructing modern distributed applications is [The Twelve-Factor App](https://12factor.net/).</span></span> <span data-ttu-id="b8df5-115">원칙 및 모범 사례 집합을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-115">It describes a set of principles and best practices.</span></span> <span data-ttu-id="b8df5-116">세 번째 요소는 *구성 및 비밀이 코드 베이스 외부에서 표면화 된* 하는 것을 규정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-116">Its third factor prescribes that *configuration and secrets be externalized outside of the code base.*</span></span>

<span data-ttu-id="b8df5-117">이러한 문제를 해결 하기 위해 .NET Core 플랫폼에는 중요 한 데이터를 프로젝트 트리 외부의 물리적 폴더에 저장 하는 [암호 관리자](/aspnet/core/security/app-secrets#secret-manager) 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-117">To address this concern, the .NET Core platform includes a [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) feature that stores sensitive data in a physical folder outside of the project tree.</span></span> <span data-ttu-id="b8df5-118">비밀은 원본 제어 외부에 있지만이 기능은 데이터를 암호화 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-118">While secrets are outside of source control, this feature doesn't encrypt data.</span></span> <span data-ttu-id="b8df5-119">**개발 목적** 으로만 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-119">It's designed for **development purposes** only.</span></span>

<span data-ttu-id="b8df5-120">더 현대적이 고 안전한 방법은 **Hashicorp Vault** 또는 **Azure Key Vault** 같은 비밀 관리 도구에서 비밀을 격리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-120">A more modern and secure practice is to isolate secrets in a secrets management tool like **Hashicorp Vault** or **Azure Key Vault**.</span></span>  <span data-ttu-id="b8df5-121">이러한 도구를 사용 하 여 암호를 외부에 저장 하 고, 환경 간에 자격 증명을 변경 하 고, 응용 프로그램 코드에서이를 참조 합니다</span><span class="sxs-lookup"><span data-stu-id="b8df5-121">These tools enable you to store secrets externally, vary credentials across environments, and reference them from application code.</span></span> <span data-ttu-id="b8df5-122">그러나 각 도구에는 복잡성과 학습 곡선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-122">However, each tool has its complexities and learning curve.</span></span>

<span data-ttu-id="b8df5-123">D 4는 비밀 관리를 간소화 하는 빌딩 블록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-123">Dapr offers a building block that simplifies managing secrets.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="b8df5-124">해결 방법</span><span class="sxs-lookup"><span data-stu-id="b8df5-124">What it solves</span></span>

<span data-ttu-id="b8df5-125">Eapr [비밀 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/secrets/secrets-overview/) 은 비밀 및 비밀 관리 도구를 사용 하는 복잡 한 작업을 추상화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-125">The Dapr [secrets building block](https://docs.dapr.io/developing-applications/building-blocks/secrets/secrets-overview/) abstracts away the complexity of working with secrets and secret management tools.</span></span>

- <span data-ttu-id="b8df5-126">통합 인터페이스를 통해 기본으로 표시 되는을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-126">It hides the underlying plumbing through a unified interface.</span></span>
- <span data-ttu-id="b8df5-127">개발 및 프로덕션에 따라 달라질 수 있는 다양 한 *플러그형* 암호 저장소 구성 요소를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-127">It supports various *pluggable* secret store components, which can vary between development and production.</span></span>
- <span data-ttu-id="b8df5-128">응용 프로그램에는 비밀 저장소 라이브러리에 대 한 직접 종속성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-128">Applications don't require direct dependencies on secret store libraries.</span></span>
- <span data-ttu-id="b8df5-129">개발자는 각 암호 저장소에 대 한 자세한 지식이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-129">Developers don't require detailed knowledge of each secret store.</span></span>

<span data-ttu-id="b8df5-130">D 4는 위의 모든 문제를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-130">Dapr handles all of the above concerns.</span></span>

<span data-ttu-id="b8df5-131">비밀에 대 한 액세스는 인증 및 권한 부여를 통해 보안이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-131">Access to the secrets is secured through authentication and authorization.</span></span> <span data-ttu-id="b8df5-132">충분 한 권한이 있는 응용 프로그램만 비밀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-132">Only an application with sufficient rights can access secrets.</span></span> <span data-ttu-id="b8df5-133">Kubernetes에서 실행 되는 응용 프로그램은 기본 제공 암호 관리 메커니즘을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-133">Applications running in Kubernetes can also use its built-in secrets management mechanism.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b8df5-134">작동 방법</span><span class="sxs-lookup"><span data-stu-id="b8df5-134">How it works</span></span>

<span data-ttu-id="b8df5-135">응용 프로그램은 다음 두 가지 방법으로 암호 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-135">Applications use the secrets building block in two ways:</span></span>

- <span data-ttu-id="b8df5-136">응용 프로그램 블록에서 직접 암호를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-136">Retrieve a secret directly from the application block.</span></span>
- <span data-ttu-id="b8df5-137">Eapr 구성 요소 구성에서 간접적으로 비밀을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-137">Reference a secret indirectly from a Dapr component configuration.</span></span>

<span data-ttu-id="b8df5-138">비밀을 직접 검색 하는 방법은 먼저 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-138">Retrieving secrets directly is covered first.</span></span> <span data-ttu-id="b8df5-139">Eapr 구성 요소 구성 파일에서 암호를 참조 하는 것은 이후 섹션에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-139">Referencing a secret from a Dapr component configuration file is addressed in a later section.</span></span>

<span data-ttu-id="b8df5-140">응용 프로그램은 암호 구성 요소를 사용할 때 사이드카와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-140">The application interacts with a Dapr sidecar when using the secrets building block.</span></span> <span data-ttu-id="b8df5-141">사이드카는 비밀 API를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-141">The sidecar exposes the secrets API.</span></span> <span data-ttu-id="b8df5-142">API는 HTTP 또는 gRPC를 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-142">The API can be called with either HTTP or gRPC.</span></span> <span data-ttu-id="b8df5-143">다음 URL을 사용 하 여 HTTP API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-143">Use the following URL to call the HTTP API:</span></span>

```http
http://localhost:<dapr-port>/v1.0/secrets/<store-name>/<name>?<metadata>
```

<span data-ttu-id="b8df5-144">URL에는 다음 세그먼트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-144">The URL contains the following segments:</span></span>

- <span data-ttu-id="b8df5-145">`<dapr-port>` 사이드카가 수신 대기 하는 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-145">`<dapr-port>` specifies the port number upon which the Dapr sidecar is listening.</span></span>
- <span data-ttu-id="b8df5-146">`<store-name>` 은 (는) Eapr 비밀 저장소의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-146">`<store-name>` specifies the name of the Dapr secret store.</span></span>
- <span data-ttu-id="b8df5-147">`<name>` 검색할 암호의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-147">`<name>` specifies  the name of the secret to retrieve.</span></span>
- <span data-ttu-id="b8df5-148">`<metadata>` 비밀에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-148">`<metadata>` provides additional information for the secret.</span></span> <span data-ttu-id="b8df5-149">이 세그먼트는 선택 사항이 며 메타 데이터 속성은 암호 저장소 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-149">This segment is optional and metadata properties differ per secret store.</span></span> <span data-ttu-id="b8df5-150">메타 데이터 속성에 대 한 자세한 내용은 [암호 API 참조]([Secrets API reference | Dapr Docs](https://docs.dapr.io/reference/api/secrets_api/))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8df5-150">For more information on metadata properties, see the [secrets API reference]([Secrets API reference | Dapr Docs](https://docs.dapr.io/reference/api/secrets_api/)).</span></span>

 > [!NOTE]
 > <span data-ttu-id="b8df5-151">위의 URL은 HTTP 또는 gRPC를 지 원하는 개발 플랫폼에서 사용할 수 있는 기본 Eapr API 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-151">The above URL represents the native Dapr API call available to any development platform that supports HTTP or gRPC.</span></span> <span data-ttu-id="b8df5-152">.NET, Java 및 Go와 같은 널리 사용 되는 플랫폼에는 고유한 사용자 지정 Api가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-152">Popular platforms like .NET, Java, and Go have their own custom APIs.</span></span>

<span data-ttu-id="b8df5-153">JSON 응답에는 암호의 키와 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-153">The JSON response contains the key and value of the secret.</span></span>

<span data-ttu-id="b8df5-154">그림 10-1에서는이 암호 API에 대 한 요청을 처리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-154">Figure 10-1 shows how Dapr handles a request for the secrets API:</span></span>

![Eapr 비밀 API를 사용 하 여 비밀을 검색 하는 다이어그램입니다.](media/secrets/secrets-flow.png)

<span data-ttu-id="b8df5-156">**그림 10-1**.</span><span class="sxs-lookup"><span data-stu-id="b8df5-156">**Figure 10-1**.</span></span> <span data-ttu-id="b8df5-157">Eapr 비밀 API를 사용 하 여 암호 검색</span><span class="sxs-lookup"><span data-stu-id="b8df5-157">Retrieving a secret with the Dapr secrets API.</span></span>

1. <span data-ttu-id="b8df5-158">서비스는 암호 저장소의 이름 및 검색할 암호와 함께 Eapr 비밀 API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-158">The service calls the Dapr secrets API, along with the name of the secret store, and secret to retrieve.</span></span>
1. <span data-ttu-id="b8df5-159">사이드카는 암호 저장소에서 지정 된 암호를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-159">The Dapr sidecar retrieves the specified secret from the secret store.</span></span>
1. <span data-ttu-id="b8df5-160">사이드카는 비밀 정보를 서비스로 돌려 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-160">The Dapr sidecar returns the secret information back to the service.</span></span>

<span data-ttu-id="b8df5-161">일부 비밀 저장소는 단일 비밀에 여러 키/값 쌍을 저장 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-161">Some secret stores support storing multiple key/value pairs in a single secret.</span></span> <span data-ttu-id="b8df5-162">이러한 시나리오의 경우 응답에는 다음 예제와 같이 단일 JSON 응답에 여러 키/값 쌍이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-162">For those scenarios, the response would contain multiple key/value pairs in a single JSON response as in the following example:</span></span>

```http
GET http://localhost:3500/v1.0/secrets/secret-store/interestRates?metadata.version_id=3
```

```json
{
  "tier1-percentage": "2.5",
  "tier2-percentage": "3.8",
  "tier3-percentage": "5.1"
}
```

<span data-ttu-id="b8df5-163">또한 응용 프로그램에서 액세스할 수 있는 모든 암호를 검색 하는 작업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-163">The Dapr secrets API also offers an operation to retrieve all the secrets the application has access to:</span></span>

```http
http://localhost:<dapr-port>/v1.0/secrets/<store-name>/bulk
```

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="b8df5-164">Dapr .NET SDK 사용</span><span class="sxs-lookup"><span data-stu-id="b8df5-164">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="b8df5-165">.NET 개발자를 위해 Dapr .NET SDK는 Dapr 비밀 관리를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-165">For .NET developers, the Dapr .NET SDK streamlines Dapr secret management.</span></span> <span data-ttu-id="b8df5-166">메서드를 살펴보겠습니다 `DaprClient.GetSecretAsync` .</span><span class="sxs-lookup"><span data-stu-id="b8df5-166">Consider the `DaprClient.GetSecretAsync` method.</span></span> <span data-ttu-id="b8df5-167">이 기능을 사용 하면 최소한의 노력으로 모든 Eapr 암호 저장소에서 직접 암호를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-167">It enables you to retrieve a secret directly from any Dapr secret store with minimal effort.</span></span> <span data-ttu-id="b8df5-168">SQL Server 데이터베이스에 대 한 연결 문자열 암호를 인출 하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-168">Here's an example of fetching a connection string secret for a SQL Server database:</span></span>

```csharp
var metadata = new Dictionary<string, string> { ["version_id"] = "3" };
Dictionary<string, string> secrets = await daprClient.GetSecretAsync("secret-store", "eshopsecrets", metadata);
string connectionString = secrets["customerdb"];
```

<span data-ttu-id="b8df5-169">메서드에 대 한 인수 `GetSecretAsync` 는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-169">Arguments for the `GetSecretAsync` method include:</span></span>

- <span data-ttu-id="b8df5-170">Eapr 비밀 저장소 구성 요소의 이름 (' secret-store ')</span><span class="sxs-lookup"><span data-stu-id="b8df5-170">The name of the Dapr secret store component ('secret-store')</span></span>
- <span data-ttu-id="b8df5-171">검색할 암호 (' eshopsecrets ')입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-171">The secret to retrieve ('eshopsecrets')</span></span>
- <span data-ttu-id="b8df5-172">선택적 메타 데이터 키/값 쌍 (' version_id = 3 ')</span><span class="sxs-lookup"><span data-stu-id="b8df5-172">Optional metadata key/value pairs ('version_id=3')</span></span>

<span data-ttu-id="b8df5-173">비밀에 여러 키/값 쌍이 포함 될 수 있으므로 메서드는 사전 개체를 사용 하 여 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-173">The method responds with a dictionary object as a secret can contain multiple key/value pairs.</span></span> <span data-ttu-id="b8df5-174">위의 예제에서 라는 암호는 `customerdb` 연결 문자열을 반환 하기 위해 컬렉션에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-174">In the example above, the secret named `customerdb` is referenced from the collection to return a connection string.</span></span>

<span data-ttu-id="b8df5-175">Dapr .NET SDK는 .NET 구성 공급자도 갖추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-175">The Dapr .NET SDK also features a .NET configuration provider.</span></span> <span data-ttu-id="b8df5-176">기본 [.Net Core 구성 API](../../core/extensions/configuration.md)에 지정 된 암호를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-176">It loads specified secrets into the underlying [.NET Core configuration API](../../core/extensions/configuration.md).</span></span> <span data-ttu-id="b8df5-177">그러면 실행 중인 응용 프로그램이 `IConfiguration` ASP.NET Core 종속성 주입에 등록 된 사전에서 비밀을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-177">The running application can then reference secrets from the `IConfiguration` dictionary that is registered in ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="b8df5-178">비밀 구성 공급자는 [Dapr.Extensions.Configuration](https://www.nuget.org/packages/Dapr.Extensions.Configuration) NuGet 패키지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-178">The secrets configuration provider is available from the [Dapr.Extensions.Configuration](https://www.nuget.org/packages/Dapr.Extensions.Configuration) NuGet package.</span></span> <span data-ttu-id="b8df5-179">공급자는 `Program.cs` ASP.NET Web API 응용 프로그램의에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-179">The provider can be registered in the `Program.cs` of an ASP.NET Web API application:</span></span>  

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureAppConfiguration(config =>
        {
            var daprClient = new DaprClientBuilder().Build();
            var secretDescriptors = new List<DaprSecretDescriptor>
            {
                new DaprSecretDescriptor("eshopsecrets")
            };
            config.AddDaprSecretStore("secret-store", secretDescriptors, daprClient);
        })
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

<span data-ttu-id="b8df5-180">위의 예제에서는 `eshopsecrets` 시작할 때 .net 구성 시스템에 비밀 컬렉션을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-180">The above example loads the `eshopsecrets` secrets collection into the .NET configuration system at startup.</span></span> <span data-ttu-id="b8df5-181">공급자를 등록 하려면 인스턴스를 사용 `DaprClient` 하 여 사이드카에서 암호 API를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-181">Registering the provider requires an instance of `DaprClient` to invoke the secrets API on the Dapr sidecar.</span></span> <span data-ttu-id="b8df5-182">다른 인수에는 비밀 저장소의 이름과 암호의 이름을 포함 하는 개체가 포함 됩니다 `DaprSecretDescriptor` .</span><span class="sxs-lookup"><span data-stu-id="b8df5-182">The other arguments include the name of the secret store and a `DaprSecretDescriptor` object with the name of the secret.</span></span>

<span data-ttu-id="b8df5-183">로드 되 면 응용 프로그램 코드에서 직접 암호를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-183">Once loaded, you can retrieve secrets directly from application code:</span></span>

```csharp
public void GetCustomer(IConfiguration config)
{
    var connectionString = config["eshopsecrets"]["customerdb"];
}
```

## <a name="secret-store-components"></a><span data-ttu-id="b8df5-184">비밀 저장소 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b8df5-184">Secret store components</span></span>

<span data-ttu-id="b8df5-185">비밀 빌딩 블록은 몇 가지 비밀 저장소 구성 요소를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-185">The secrets building block supports several secret store components.</span></span> <span data-ttu-id="b8df5-186">작성 시 다음과 같은 비밀 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-186">At the time of writing, the following secret stores are available:</span></span>

- <span data-ttu-id="b8df5-187">환경 변수</span><span class="sxs-lookup"><span data-stu-id="b8df5-187">Environment Variables</span></span>
- <span data-ttu-id="b8df5-188">로컬 파일</span><span class="sxs-lookup"><span data-stu-id="b8df5-188">Local file</span></span>
- <span data-ttu-id="b8df5-189">Kubernetes 비밀</span><span class="sxs-lookup"><span data-stu-id="b8df5-189">Kubernetes secrets</span></span>
- <span data-ttu-id="b8df5-190">AWS 암호 관리자</span><span class="sxs-lookup"><span data-stu-id="b8df5-190">AWS Secrets Manager</span></span>
- <span data-ttu-id="b8df5-191">Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b8df5-191">Azure Key Vault</span></span>
- <span data-ttu-id="b8df5-192">GCP 암호 관리자</span><span class="sxs-lookup"><span data-stu-id="b8df5-192">GCP Secret Manager</span></span>
- <span data-ttu-id="b8df5-193">HashiCorp 자격 증명 모음</span><span class="sxs-lookup"><span data-stu-id="b8df5-193">HashiCorp Vault</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8df5-194">환경 변수와 로컬 파일 구성 요소는 개발 작업 전용으로 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-194">The environment variables and local file components are designed for development workloads only.</span></span>

<span data-ttu-id="b8df5-195">다음 섹션에서는 비밀 저장소를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-195">The following sections show how to configure a secret store.</span></span>

### <a name="configuration"></a><span data-ttu-id="b8df5-196">구성</span><span class="sxs-lookup"><span data-stu-id="b8df5-196">Configuration</span></span>

<span data-ttu-id="b8df5-197">Eapr 구성 요소 구성 파일을 사용 하 여 비밀 저장소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-197">You configure a secret store using a Dapr component configuration file.</span></span> <span data-ttu-id="b8df5-198">파일의 일반적인 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-198">The typical structure of the file is shown below:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: [component name]
  namespace: [namespace]
spec:
  type: secretstores.[secret store type]
  version: [secret store version]
  metadata:
  - name: [property name]
    value: [property value]
```

<span data-ttu-id="b8df5-199">모든 Eapr 구성 요소 구성 파일에는 `name` 선택적 값과 함께가 필요 `namespace` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-199">All Dapr component configuration files require a `name` along with an optional `namespace` value.</span></span> <span data-ttu-id="b8df5-200">또한 `type` 섹션의 필드는 `spec` 비밀 저장소 구성 요소의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-200">Additionally, the `type` field in the `spec` section specifies the type of secret store component.</span></span> <span data-ttu-id="b8df5-201">섹션의 속성은 `metadata` 암호 저장소 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-201">The properties in the `metadata` section differ per secret store.</span></span>

### <a name="indirectly-consume-dapr-secrets"></a><span data-ttu-id="b8df5-202">매우 Apr 암호를 간접적으로 사용</span><span class="sxs-lookup"><span data-stu-id="b8df5-202">Indirectly consume Dapr secrets</span></span>

<span data-ttu-id="b8df5-203">이 챕터의 앞부분에서 설명한 것 처럼 응용 프로그램은 구성 요소 구성 파일에서 암호를 참조 하 여 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-203">As mentioned earlier in this chapter, applications can also consume secrets by referencing them in component configuration files.</span></span> <span data-ttu-id="b8df5-204">상태를 저장 하는 데 Redis cache를 사용 하는 [상태 관리 구성 요소](state-management.md) 를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-204">Consider a [state management component](state-management.md) that uses Redis cache for storing state:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: e$h0p0nD@pr
```

<span data-ttu-id="b8df5-205">위의 구성 파일에는 Redis 서버에 연결 하기 위한 **일반 텍스트** 암호가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-205">The above configuration file contains a **clear-text** password for connecting to the Redis server.</span></span> <span data-ttu-id="b8df5-206">**하드 코드** 된 암호는 항상 잘못 된 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-206">**Hardcoded** passwords are always a bad idea.</span></span> <span data-ttu-id="b8df5-207">이 구성 파일을 공용 리포지토리로 푸시하여 암호를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-207">Pushing this configuration file to a public repository would expose the password.</span></span> <span data-ttu-id="b8df5-208">암호를 비밀 저장소에 저장 하면이 시나리오를 크게 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-208">Storing the password in a secret store would dramatically improve this scenario.</span></span>

<span data-ttu-id="b8df5-209">다음 예제에서는 여러 가지 암호 저장소를 사용 하 여이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-209">The following examples demonstrate this using several different secret stores.</span></span>

### <a name="local-file"></a><span data-ttu-id="b8df5-210">로컬 파일</span><span class="sxs-lookup"><span data-stu-id="b8df5-210">Local file</span></span>

<span data-ttu-id="b8df5-211">로컬 파일 구성 요소는 개발 시나리오를 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-211">The local file component is designed for development scenarios.</span></span> <span data-ttu-id="b8df5-212">JSON 파일 내에서 로컬 파일 시스템에 대 한 암호를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-212">It stores secrets on the local filesystem inside a JSON file.</span></span> <span data-ttu-id="b8df5-213">다음은 라는 예제 `eshop-secrets.json` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-213">Here's an example named `eshop-secrets.json`.</span></span> <span data-ttu-id="b8df5-214">Redis에 대 한 단일 암호 a 암호를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-214">It contains a single secret - a password for Redis:</span></span>

```json
{
  "eShopRedisPassword": "e$h0p0nD@pr"
}
```

<span data-ttu-id="b8df5-215">이 파일 `components` 은 Eapr 응용 프로그램을 실행할 때 지정 하는 폴더에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-215">You place this file in a `components` folder that you specify when running the Dapr application.</span></span>

<span data-ttu-id="b8df5-216">다음 비밀 저장소 구성 파일은 JSON 파일을 비밀 저장소로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-216">The following secret store configuration file consumes the JSON file as a secret store.</span></span> <span data-ttu-id="b8df5-217">또한 폴더에 배치 됩니다 `components` .</span><span class="sxs-lookup"><span data-stu-id="b8df5-217">It's also placed in the `components` folder:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-local-secret-store
  namespace: eshop
spec:
  type: secretstores.local.file
  version: v1
  metadata:
  - name: secretsFile
    value: ./components/eshop-secrets.json
  - name: nestedSeparator
    value: ":"
```

<span data-ttu-id="b8df5-218">구성 요소 `secretstore.local.file` 형식이 인 경우</span><span class="sxs-lookup"><span data-stu-id="b8df5-218">The component type is `secretstore.local.file`.</span></span> <span data-ttu-id="b8df5-219">`secretsFile`Metadata 요소는 비밀 파일의 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-219">The `secretsFile` metadata element specifies the path to the secrets file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8df5-220">비밀 파일의 경로는 절대 경로 또는 상대 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-220">The path to a secrets file can be a absolute or relative path.</span></span> <span data-ttu-id="b8df5-221">상대 경로는 응용 프로그램이 시작 되는 폴더를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-221">The relative path is based on the folder in which the application starts.</span></span> <span data-ttu-id="b8df5-222">이 예제에서 폴더는 `components` .net 응용 프로그램이 포함 된 디렉터리의 하위 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-222">In the example, the `components` folder is a sub-folder of the directory that contains the .NET application.</span></span>

<span data-ttu-id="b8df5-223">응용 프로그램 폴더에서 경로를 명령줄 인수로 지정 하 여 Eapr 응용 프로그램을 시작 합니다 `components` .</span><span class="sxs-lookup"><span data-stu-id="b8df5-223">From the application folder, start the Dapr application specifying the `components` path as a command-line argument:</span></span>

```console
dapr run --app-id basket-api --components-path ./components dotnet run
```

> [!NOTE]
> <span data-ttu-id="b8df5-224">위의 예제는 자체 호스팅 모드에서 실행 중인 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-224">This above example applies to running Dapr in self-hosted mode.</span></span> <span data-ttu-id="b8df5-225">Kubernetes 호스팅의 경우 볼륨 탑재를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-225">For Kubernetes hosting, consider using volume mounts.</span></span>

<span data-ttu-id="b8df5-226">`nestedSeparator`Eapr 구성 파일의는 JSON 계층 구조를 *평면화* 하는 문자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-226">The `nestedSeparator` in a Dapr configuration file specifies a character to *flatten* a JSON hierarchy.</span></span> <span data-ttu-id="b8df5-227">다음 코드 조각을 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="b8df5-227">Consider the following snippet:</span></span>

```json
{
    "redisPassword": "some password",
    "connectionStrings": {
        "customerdb": "some connection string",
        "productdb": "some connection string"
    }
}
```

<span data-ttu-id="b8df5-228">콜론을 구분 기호로 사용 하 여 `customerdb` 키를 사용 하 여 연결 문자열을 검색할 수 있습니다 `connectionStrings:customerdb` .</span><span class="sxs-lookup"><span data-stu-id="b8df5-228">Using a colon as a separator, you can retrieve the `customerdb` connection-string using the key `connectionStrings:customerdb`.</span></span>

> [!NOTE]
> <span data-ttu-id="b8df5-229">콜론은 `:` 기본 구분 기호 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-229">The colon `:` is the default separator value.</span></span>

<span data-ttu-id="b8df5-230">다음 예제에서 상태 관리 구성 파일은 로컬 암호 저장소 구성 요소를 참조 하 여 Redis 서버에 연결 하기 위한 암호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-230">In the next example, a state management configuration file references the local secret store component to obtain the password for connecting to the Redis server:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    secretKeyRef:
      name: eShopRedisPassword
      key: eShopRedisPassword
auth:
  secretStore: eshop-local-secret-store
```

<span data-ttu-id="b8df5-231">`secretKeyRef`요소는 암호를 포함 하는 암호를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-231">The `secretKeyRef` element references the secret containing the password.</span></span> <span data-ttu-id="b8df5-232">이전의 *일반 텍스트* 값을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-232">It replaces the earlier *clear-text* value.</span></span> <span data-ttu-id="b8df5-233">비밀 이름 및 키 이름인는 비밀을 `eShopRedisPassword` 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-233">The secret name and the key name, `eShopRedisPassword`, reference the secret.</span></span> <span data-ttu-id="b8df5-234">비밀 관리 구성 요소의 이름은 `eshop-local-secret-store` `auth` metadata 요소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-234">The name of the secret management component `eshop-local-secret-store` is found in the `auth` metadata element.</span></span>

<span data-ttu-id="b8df5-235">`eShopRedisPassword`암호 참조의 이름과 키에 대해가 동일한 이유를 궁금할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-235">You might wonder why `eShopRedisPassword` is identical for both the name and key in the secret reference.</span></span> <span data-ttu-id="b8df5-236">로컬 파일 비밀 저장소에서 비밀은 별도의 이름으로 식별 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-236">In the local file secret store, secrets aren't identified with a separate name.</span></span> <span data-ttu-id="b8df5-237">시나리오는 다음 예제에서 Kubernetes 암호를 사용 하는 것과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-237">The scenario will be different in the next example using Kubernetes secrets.</span></span>

### <a name="kubernetes-secret"></a><span data-ttu-id="b8df5-238">Kubernetes 암호</span><span class="sxs-lookup"><span data-stu-id="b8df5-238">Kubernetes secret</span></span>

<span data-ttu-id="b8df5-239">이 두 번째 예제에서는 Kubernetes에서 실행 되는 4Apr 응용 프로그램을 중심으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-239">This second example focuses on a Dapr application running in Kubernetes.</span></span> <span data-ttu-id="b8df5-240">Kubernetes에서 제공 하는 표준 비밀 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-240">It uses the standard secrets mechanism that Kubernetes offers.</span></span> <span data-ttu-id="b8df5-241">Kubernetes CLI ()를 사용 `kubectl` 하 여 `eshop-redis-secret` 암호를 포함 하는 라는 암호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-241">Use the Kubernetes CLI (`kubectl`) to create a secret named `eshop-redis-secret` that contains the password:</span></span>

```console
kubectl create secret generic eshopsecrets --from-literal=redisPassword=e$h0p0nD@pr -n eshop
```

<span data-ttu-id="b8df5-242">일단 만들어지면 상태 관리를 위해 구성 요소 구성 파일에서 암호를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-242">Once created, you can reference the secret in the component configuration file for state management:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: eshopsecrets
      key: redisPassword
auth:
  secretStore: kubernetes
```

<span data-ttu-id="b8df5-243">`secretKeyRef`요소는 각각 Kubernetes 암호와 비밀 키, 및의 이름을 지정 합니다 `eshopsecrets` `redisPassword` .</span><span class="sxs-lookup"><span data-stu-id="b8df5-243">The `secretKeyRef` element specifies the name of the Kubernetes secret and the secret's key, `eshopsecrets`, and `redisPassword` respectively.</span></span> <span data-ttu-id="b8df5-244">`auth`메타 데이터 섹션은 Kubernetes 암호 관리 구성 요소를 사용 하도록 d 4에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-244">The `auth` metadata section instructs Dapr to use the Kubernetes secrets management component.</span></span>

> [!NOTE]
> <span data-ttu-id="b8df5-245">Kubernetes 암호를 사용 하는 경우에는 Auth가 기본값이 며 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-245">Auth is the default value when using Kubernetes secrets and can be omitted.</span></span>

<span data-ttu-id="b8df5-246">프로덕션 설정에서 비밀은 일반적으로 자동화 된 CI/CD 파이프라인의 일부로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-246">In a production setting, secrets are typically created as part of an automated CI/CD pipeline.</span></span> <span data-ttu-id="b8df5-247">이렇게 하면 충분 한 권한이 있는 사용자만 암호에 액세스 하 고 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-247">Doing so ensures only people with sufficient permissions can access and change the secrets.</span></span> <span data-ttu-id="b8df5-248">개발자는 암호의 실제 값을 알지 못해도 구성 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-248">Developers create configuration files without knowing the actual value of the secrets.</span></span>

### <a name="azure-key-vault"></a><span data-ttu-id="b8df5-249">Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b8df5-249">Azure Key Vault</span></span>

<span data-ttu-id="b8df5-250">다음 예제는 실제 프로덕션 시나리오에 맞게 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-250">The next example is geared toward a real-world production scenario.</span></span> <span data-ttu-id="b8df5-251">비밀 저장소로 **Azure Key Vault** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-251">It uses **Azure Key Vault** as the secret store.</span></span> <span data-ttu-id="b8df5-252">Azure Key Vault는 암호를 클라우드에 안전 하 게 저장할 수 있게 해 주는 관리 되는 Azure 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-252">Azure Key Vault is a managed Azure service that enables secrets to be stored securely in the cloud.</span></span>

<span data-ttu-id="b8df5-253">이 예제가 작동 하려면 다음 필수 구성 요소를 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-253">For this example to work, the following prerequisites must be satisfied:</span></span>

- <span data-ttu-id="b8df5-254">Azure 구독에 대 한 관리 액세스를 보호 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-254">You've secured administrative access to an Azure subscription.</span></span>
- <span data-ttu-id="b8df5-255">`eshopkv` `redisPassword` Redis 서버에 연결 하기 위한 암호를 포함 하는 라는 암호를 포함 하는 라는 Azure Key Vault를 프로 비전 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-255">You've provisioned an Azure Key Vault named `eshopkv` that holds a secret named `redisPassword` that contains the password for connecting to the Redis server.</span></span>
- <span data-ttu-id="b8df5-256">Azure Active Directory에서 [서비스 주체](/azure/active-directory/develop/howto-create-service-principal-portal) 를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-256">You've created [service principal](/azure/active-directory/develop/howto-create-service-principal-portal) in Azure Active Directory.</span></span>
- <span data-ttu-id="b8df5-257">로컬 파일 시스템에이 서비스 사용자에 대 한 X509 인증서 (공개 키와 개인 키 둘 다 포함)를 설치 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-257">You've installed an X509 certificate for this service principal (containing both the public and private key) on the local filesystem.</span></span>

> [!NOTE]
> <span data-ttu-id="b8df5-258">서비스 주체는 응용 프로그램에서 Azure 서비스를 인증 하는 데 사용할 수 있는 id입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-258">A service principal is an identity that can be used by an application to authenticate an Azure service.</span></span> <span data-ttu-id="b8df5-259">서비스 주체는 X509 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-259">The service principal uses a X509 certificate.</span></span> <span data-ttu-id="b8df5-260">응용 프로그램은이 인증서를 자격 증명으로 사용 하 여 자신을 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-260">The application uses this certificate as a credential to authenticate itself.</span></span>

<span data-ttu-id="b8df5-261">[Azure Key Vault 암호 저장소 설명서](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault/) 는 Key Vault 환경을 만들고 구성 하는 단계별 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-261">The [Dapr Azure Key Vault secret store documentation](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault/) provides step-by-step instructions to create and configure a Key Vault environment.</span></span>

#### <a name="use-key-vault-when-running-in-self-hosted-mode"></a><span data-ttu-id="b8df5-262">자체 호스팅 모드로 실행 하는 경우 Key Vault 사용</span><span class="sxs-lookup"><span data-stu-id="b8df5-262">Use Key Vault when running in self-hosted mode</span></span>

<span data-ttu-id="b8df5-263">다음 구성 파일을 사용 하 여 Eapr 자체 호스팅 모드에서 Azure Key Vault를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-263">Consuming Azure Key Vault in Dapr self-hosted mode requires the following configuration file:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-azurekv-secret-store
  namespace: eshop
spec:
  type: secretstores.azure.keyvault
  version: v1
  metadata:
  - name: vaultName
    value: eshopkv
  - name: spnTenantId
    value: "619926af-a7c3-4e95-93ed-4ecc4e3e652b"
  - name: spnClientId
    value: "6cf48032-6c38-43be-9d6f-2a43ce736b09"
  - name: spnCertificateFile
    value : "azurekv-spn-cert.pfx"
```

<span data-ttu-id="b8df5-264">비밀 저장소 `secretstores.azure.keyvault` 형식이 인 경우</span><span class="sxs-lookup"><span data-stu-id="b8df5-264">The secret store type is `secretstores.azure.keyvault`.</span></span> <span data-ttu-id="b8df5-265">`metadata`Key Vault에 대 한 액세스를 구성 하는 요소에는 다음 속성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-265">The `metadata` element to configure access to Key Vault requires the following properties:</span></span>

- <span data-ttu-id="b8df5-266">에는 `vaultName` Azure Key Vault 이름이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-266">The `vaultName` contains the name of the Azure Key Vault.</span></span>
- <span data-ttu-id="b8df5-267">에는 `spnTenantId` Key Vault에 대 한 인증에 사용 되는 서비스 사용자의 *테 넌 트 ID가* 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-267">The `spnTenantId` contains the *tenant ID* of the service principal used to authenticate against the Key Vault.</span></span>
- <span data-ttu-id="b8df5-268">에는 `spnClientId` Key Vault에 대 한 인증에 사용 되는 서비스 주체의 *앱 ID* 가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-268">The `spnClientId` contains the *app ID* of the service principal used to authenticate against the Key Vault.</span></span>
- <span data-ttu-id="b8df5-269">에는 `spnCertificateFile` 서비스 사용자가 Key Vault에 대해 인증할 인증서 파일에 대 한 경로가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-269">The `spnCertificateFile` contains the path to the certificate file for the service principal to authenticate against the Key Vault.</span></span>

> [!TIP]
> <span data-ttu-id="b8df5-270">Azure Portal 또는 Azure CLI에서 서비스 사용자 정보를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-270">You can copy the service principal information from the Azure portal or Azure CLI .</span></span>

<span data-ttu-id="b8df5-271">이제 응용 프로그램은 Azure Key Vault에서 Redis 암호를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-271">Now the application can retrieve the Redis password from the Azure Key Vault.</span></span>

#### <a name="use-key-vault-when-running-on-kubernetes"></a><span data-ttu-id="b8df5-272">Kubernetes에서 실행 하는 경우 Key Vault 사용</span><span class="sxs-lookup"><span data-stu-id="b8df5-272">Use Key Vault when running on Kubernetes</span></span>

<span data-ttu-id="b8df5-273">Kubernetes와 함께 Azure Key Vault를 사용 하려면 Azure Key Vault에 대해 인증 하는 서비스 사용자도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-273">Consuming Azure Key Vault with Dapr and Kubernetes also requires a service principal to authenticate against the Azure Key Vault.</span></span>

<span data-ttu-id="b8df5-274">먼저 kubectl CLI 도구를 사용 하 여 인증서 파일을 포함 하는 *Kubernetes 암호* 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-274">First, create a *Kubernetes secret* that contains a certificate file using the kubectl CLI tool:</span></span>

```console
kubectl create secret generic [k8s_spn_secret_name] --from-file=[pfx_certificate_file_local_path] -n eshop
```

<span data-ttu-id="b8df5-275">명령에는 다음 두 명령줄 인수가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-275">The command requires two command-line arguments:</span></span>

- <span data-ttu-id="b8df5-276">`[k8s_spn_secret_name]` Kubernetes secret store의 비밀 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-276">`[k8s_spn_secret_name]` is the secret name in Kubernetes secret store.</span></span>
- <span data-ttu-id="b8df5-277">`[pfx_certificate_file_local_path]` X509 인증서 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-277">`[pfx_certificate_file_local_path]` is the path of X509 certificate file.</span></span>

<span data-ttu-id="b8df5-278">일단 만들어지면 비밀 저장소 구성 요소 구성 파일에서 Kubernetes 암호를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-278">Once created, you can reference the Kubernetes secret in the secret store component configuration file:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-azurekv-secret-store
  namespace: eshop
spec:
  type: secretstores.azure.keyvault
  version: v1
  metadata:
  - name: vaultName
    value: [your_keyvault_name]
  - name: spnTenantId
    value: "619926af-a7c3-4e95-93ed-4ecc4e3e652b"
  - name: spnClientId
    value: "6cf48032-6c38-43be-9d6f-2a43ce736b09"
  - name: spnCertificate
    secretKeyRef:
      name: [k8s_spn_secret_name]
      key: [pfx_certificate_file_local_name]
auth:
    secretStore: kubernetes
```

<span data-ttu-id="b8df5-279">이 시점에서 Kubernetes에서 실행 되는 응용 프로그램은 Azure Key Vault에서 Redis 암호를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-279">At this point, an application running in Kubernetes can retrieve the Redis password from the Azure Key Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8df5-280">서비스 사용자에 대 한 X509 인증서 파일을 안전한 장소에 보관 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-280">It's critical to keep the X509 certificate file for the service principal in a safe place.</span></span> <span data-ttu-id="b8df5-281">소스 코드 리포지토리 외부의 잘 알려진 폴더에 저장 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-281">It's best to place it in a well-known folder outside the source-code repository.</span></span> <span data-ttu-id="b8df5-282">구성 파일은이 잘 알려진 폴더에서 인증서 파일을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-282">The configuration file can then reference the certificate file from this well-known folder.</span></span> <span data-ttu-id="b8df5-283">로컬 개발 컴퓨터에서는 인증서를 폴더에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-283">On a local development machine, you're responsible for copying the certificate to the folder.</span></span> <span data-ttu-id="b8df5-284">자동 배포의 경우 파이프라인이 응용 프로그램이 배포 된 컴퓨터에 인증서를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-284">For automated deployments, the pipeline will copy the certificate to the machine where the application is deployed.</span></span> <span data-ttu-id="b8df5-285">환경 마다 다른 서비스 주체를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-285">It's a best practice to use a different service principal per environment.</span></span> <span data-ttu-id="b8df5-286">이렇게 하면 개발 환경의 서비스 주체가 프로덕션 환경의 암호에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-286">Doing so prevents the service principal from a DEVELOPMENT environment to access secrets in a PRODUCTION environment.</span></span>

<span data-ttu-id="b8df5-287">Azure Kubernetes 서비스 (AKS)에서 실행 되는 경우 [Azure 관리 id](/azure/active-directory/managed-identities-azure-resources/overview) 를 사용 하 여 Azure Key Vault에 대 한 인증을 받는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-287">When running in  Azure Kubernetes Service (AKS), it's preferable to use an [Azure Managed Identity](/azure/active-directory/managed-identities-azure-resources/overview) for authenticating against Azure Key Vault.</span></span> <span data-ttu-id="b8df5-288">관리 id는이 책의 범위를 벗어나지만 관리 되는 [id를 사용 하 여 Azure Key Vault](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault-managed-identity/) 설명서에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-288">Managed identities are outside of the scope of this book, but explained in the [Azure Key Vault with managed identities](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault-managed-identity/) documentation.</span></span>

### <a name="scope-secrets"></a><span data-ttu-id="b8df5-289">범위 비밀</span><span class="sxs-lookup"><span data-stu-id="b8df5-289">Scope secrets</span></span>

<span data-ttu-id="b8df5-290">비밀 범위를 사용 하면 응용 프로그램에서 액세스할 수 있는 암호를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-290">Secret scopes allow you to control which secrets your application can access.</span></span> <span data-ttu-id="b8df5-291">Eapr 사이드카 구성 파일에서 범위를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-291">You configure scopes in a Dapr sidecar configuration file.</span></span> <span data-ttu-id="b8df5-292">[Eapr 구성 설명서](https://docs.dapr.io/operations/configuration/configuration-overview/) 에서는 비밀 범위 지정을 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-292">The [Dapr configuration documentation](https://docs.dapr.io/operations/configuration/configuration-overview/) provides instructions for scoping secrets.</span></span>

<span data-ttu-id="b8df5-293">비밀 범위를 포함 하는 Eapr 사이드카 구성 파일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-293">Here's an example of a Dapr sidecar configuration file that contains secret scopes:</span></span>

```yml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: dapr-config
  namespace: eshop
spec:
  tracing:
    samplingRate: "1"
  secrets:
    scopes:
      - storeName: eshop-azurekv-secret-store
        defaultAccess: allow
        deniedSecrets: ["redisPassword", "apiKey"]
```

<span data-ttu-id="b8df5-294">비밀 저장소 당 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-294">You specify scopes per secret store.</span></span> <span data-ttu-id="b8df5-295">위의 예제에서 비밀 저장소의 이름은 `eshop-azurekv-secret-store` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-295">In the above example, the secret store is named `eshop-azurekv-secret-store`.</span></span> <span data-ttu-id="b8df5-296">다음 속성을 사용 하 여 암호에 대 한 액세스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-296">You configure access to secrets using the following properties:</span></span>

| <span data-ttu-id="b8df5-297">속성</span><span class="sxs-lookup"><span data-stu-id="b8df5-297">Property</span></span>         | <span data-ttu-id="b8df5-298">값</span><span class="sxs-lookup"><span data-stu-id="b8df5-298">Value</span></span>               | <span data-ttu-id="b8df5-299">설명</span><span class="sxs-lookup"><span data-stu-id="b8df5-299">Description</span></span>                                                                                                                       |
|------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| `defaultAccess`  | <span data-ttu-id="b8df5-300">`allow` 또는 `deny`</span><span class="sxs-lookup"><span data-stu-id="b8df5-300">`allow` or `deny`</span></span>   | <span data-ttu-id="b8df5-301">지정 된 암호 저장소의 *모든* 암호에 대 한 액세스를 허용 하거나 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-301">Allows or denies access to *all* secrets in the specified secret store.</span></span> <span data-ttu-id="b8df5-302">이 속성은 선택 사항이 며 기본값은 `allow` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-302">This property is optional with a default value of `allow`.</span></span> |
| `allowedSecrets` | <span data-ttu-id="b8df5-303">비밀 키 목록</span><span class="sxs-lookup"><span data-stu-id="b8df5-303">List of secret keys</span></span> | <span data-ttu-id="b8df5-304">배열에 지정 된 비밀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-304">Secrets specified in the array will be accessible.</span></span> <span data-ttu-id="b8df5-305">이 속성은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-305">This property is optional.</span></span>                                                     |
| `deniedSecrets`  | <span data-ttu-id="b8df5-306">비밀 키 목록</span><span class="sxs-lookup"><span data-stu-id="b8df5-306">List of secret keys</span></span> | <span data-ttu-id="b8df5-307">배열에 지정 된 암호에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-307">Secrets specified in the array will NOT be accessible.</span></span> <span data-ttu-id="b8df5-308">이 속성은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-308">This property is optional.</span></span>                                                 |

<span data-ttu-id="b8df5-309">`allowedSecrets`및 `deniedSecrets` 속성은 속성 보다 우선적으로 적용 `defaultAccess` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-309">The `allowedSecrets` and `deniedSecrets` properties take precedence over the `defaultAccess` property.</span></span> <span data-ttu-id="b8df5-310">및 목록을 지정 한다고 가정 `defaultAccess: allowed` `allowedSecrets` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-310">Imagine specifying `defaultAccess: allowed` and an `allowedSecrets` list.</span></span> <span data-ttu-id="b8df5-311">이 경우 `allowedSecrets` 응용 프로그램에서 목록의 암호만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-311">In this case, only the secrets in the `allowedSecrets` list would be accessible by the application.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="b8df5-312">참조 응용 프로그램: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="b8df5-312">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="b8df5-313">EShopOnDapr reference 응용 프로그램은 두 비밀에 대해 암호 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-313">The eShopOnDapr reference application uses the secrets building block for two secrets:</span></span>

- <span data-ttu-id="b8df5-314">Redis cache에 연결 하기 위한 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-314">The password for connecting to the Redis cache.</span></span>
- <span data-ttu-id="b8df5-315">Twilio Sendgrid API를 사용 하기 위한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-315">The API-key for using the Twilio Sendgrid API.</span></span> <span data-ttu-id="b8df5-316">응용 프로그램은 Twillio를 사용 하 여 [바인딩 빌딩 블록 챕터](bindings.md)에 설명 된 것 처럼, eapr 출력 바인딩을 사용 하 여 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-316">The application uses Twillio to send emails using a Dapr output binding (as described in the [bindings building block chapter](bindings.md)).</span></span>

<span data-ttu-id="b8df5-317">Docker Compose를 사용 하 여 응용 프로그램을 실행 하는 경우 **로컬 파일** 비밀 저장소가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-317">When running the application using Docker Compose, the **local file** secret store is used.</span></span> <span data-ttu-id="b8df5-318">구성 요소 구성 파일은 `eshop-secretstore.yaml` `dapr/components` eShopOnDapr 리포지토리의 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-318">The component configuration file `eshop-secretstore.yaml` is found in the `dapr/components` folder of the eShopOnDapr repository:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-secretstore
  namespace: eshop
spec:
  type: secretstores.local.file
  version: v1
  metadata:
  - name: secretsFile
    value: ./components/eshop-secretstore.json
```

<span data-ttu-id="b8df5-319">구성 파일은 `eshop-secretstore.json` 동일한 폴더에 있는 로컬 저장소 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-319">The configuration file references the local store file `eshop-secretstore.json` located in the same folder:</span></span>

```json
{
    "redisPassword": "**********",
    "sendgridAPIKey": "**********"
}
```

<span data-ttu-id="b8df5-320">폴더는 명령줄 `components` 에서 지정 되 고,이 폴더는 Eapr 사이드카 컨테이너 내의 로컬 폴더로 탑재 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-320">The `components` folder is specified in the command-line and mounted as a local folder inside the Dapr sidecar container.</span></span> <span data-ttu-id="b8df5-321">`docker-compose.override.yml`볼륨 탑재를 지정 하는 리포지토리 루트에 있는 파일의 조각은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-321">Here's a snippet from the `docker-compose.override.yml` file in the repository root that specifies the volume mount:</span></span>

```yaml
  ordering-backgroundtasks-dapr:
    command: ["./daprd",
      "-app-id", "ordering-backgroundtasks",
      "-app-port", "80",
      "-dapr-grpc-port", "50004",
      "-components-path", "/components",
      "-config", "/configuration/eshop-config.yaml"
      ]
    volumes:
      - "./dapr/components/:/components"
      - "./dapr/configuration/:/configuration"
```

> [!NOTE]
> <span data-ttu-id="b8df5-322">Docker Compose 재정의 파일은 환경 특정 구성 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-322">The Docker Compose override file contains environmental specific configuration values.</span></span>

<span data-ttu-id="b8df5-323">`/components`볼륨 탑재 및 `--components-path` 명령줄 인수는 시작 명령에 전달 됩니다 `daprd` .</span><span class="sxs-lookup"><span data-stu-id="b8df5-323">The `/components` volume mount and `--components-path` command-line argument are passed into the `daprd` startup command.</span></span>

<span data-ttu-id="b8df5-324">구성 된 후에는 다른 구성 요소 구성 파일 에서도 암호를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-324">Once configured, other component configuration files can also reference the secrets.</span></span> <span data-ttu-id="b8df5-325">비밀을 사용 하는 게시/구독 구성 요소 구성의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-325">Here's an example of the Publish/Subscribe component configuration consuming secrets:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub
  namespace: eshop
spec:
  type: pubsub.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: redisPassword
auth:
  secretStore: eshop-secretstore
```

<span data-ttu-id="b8df5-326">위의 예제에서 로컬 Redis 저장소는 비밀을 참조 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-326">In the preceding example, the local Redis store is used to reference secrets.</span></span>

## <a name="summary"></a><span data-ttu-id="b8df5-327">요약</span><span class="sxs-lookup"><span data-stu-id="b8df5-327">Summary</span></span>

<span data-ttu-id="b8df5-328">4Apr 비밀 빌딩 블록은 암호 및 연결 문자열과 같은 중요 한 구성 설정을 저장 하 고 검색 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-328">The Dapr secrets building block provides capabilities for storing and retrieving sensitive configuration settings like passwords and connection-strings.</span></span> <span data-ttu-id="b8df5-329">비밀을 비공개로 유지 하 고 실수로 공개 되지 않도록 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-329">It keeps secrets private and prevents them from being accidentally disclosed.</span></span>

<span data-ttu-id="b8df5-330">빌딩 블록은 다양 한 암호 저장소를 지원 하 고,이를 통해 복잡 한 암호를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-330">The building block supports several different secret stores and hides their complexity with the Dapr secrets API.</span></span>

<span data-ttu-id="b8df5-331">Dapr .NET SDK는 `DaprClient` 암호를 검색 하는 개체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-331">The Dapr .NET SDK provides a `DaprClient` object to retrieve secrets.</span></span> <span data-ttu-id="b8df5-332">또한 .NET Core 구성 시스템에 암호를 추가 하는 .NET 구성 공급자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-332">It also includes a .NET configuration provider that adds secrets to the .NET Core configuration system.</span></span> <span data-ttu-id="b8df5-333">로드 된 후에는 .NET 코드에서 이러한 암호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-333">Once loaded, you can consume these secrets in your .NET code.</span></span>

<span data-ttu-id="b8df5-334">비밀 범위를 사용 하 여 특정 비밀에 대 한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8df5-334">You can use secret scopes to control access to specific secrets.</span></span>

## <a name="references"></a><span data-ttu-id="b8df5-335">참조</span><span class="sxs-lookup"><span data-stu-id="b8df5-335">References</span></span>

- [<span data-ttu-id="b8df5-336">Twelve-Factor 응용 프로그램 외</span><span class="sxs-lookup"><span data-stu-id="b8df5-336">Beyond the Twelve-Factor Application</span></span>](https://tanzu.vmware.com/content/blog/beyond-the-twelve-factor-app)

>[!div class="step-by-step"]
><span data-ttu-id="b8df5-337">[이전](observability.md)
>[다음](summary.md)</span><span class="sxs-lookup"><span data-stu-id="b8df5-337">[Previous](observability.md)
[Next](summary.md)</span></span>
