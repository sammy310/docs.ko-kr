---
title: 4Apr 비밀 빌딩 블록
description: 비밀 구성 요소에 대 한 설명, 해당 기능, 이점 및 적용 방법
author: edwinvw
ms.date: 02/17/2021
ms.openlocfilehash: 52b899b4d496aab6762f69bbee99faecfcd23d59
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623748"
---
# <a name="the-dapr-secrets-building-block"></a>4Apr 비밀 빌딩 블록

엔터프라이즈 응용 프로그램에는 암호가 필요 합니다. 일반적인 예제는 다음을 포함합니다.

- 사용자 이름 및 암호를 포함 하는 데이터베이스 연결 문자열입니다.
- 외부 web API를 호출 하는 API 키입니다.
- 외부 시스템을 인증 하기 위한 클라이언트 인증서입니다.

암호는 응용 프로그램 외부에 공개 되지 않도록 신중 하 게 관리 해야 합니다.

오래 전에는 응용 프로그램 코드 베이스 내의 구성 파일에 응용 프로그램 암호를 저장 하는 것이 일반적 이었습니다. .NET 개발자는 *web.config* 파일을 fondly 회수할 것입니다. 간단 하 게 구현 하는 동안 코드와 함께 비밀을 통합 하는 것은 안전 하지 않습니다. 일반적인 잘못 된 단계는 공용 GIT 리포지토리로 푸시 될 때 파일을 포함 하 여 전 세계에 암호를 노출 하는 것입니다.

최신 배포 응용 프로그램을 구성 하는 데 널리 승인 된 방법은 [Twelve-Factor 앱](https://12factor.net/)입니다. 원칙 및 모범 사례 집합을 설명 합니다. 세 번째 요소는 *구성 및 비밀이 코드 베이스 외부에서 표면화 된* 하는 것을 규정 합니다.

이러한 문제를 해결 하기 위해 .NET Core 플랫폼에는 중요 한 데이터를 프로젝트 트리 외부의 물리적 폴더에 저장 하는 [암호 관리자](/aspnet/core/security/app-secrets#secret-manager) 기능이 포함 되어 있습니다. 비밀은 원본 제어 외부에 있지만이 기능은 데이터를 암호화 하지 않습니다. **개발 목적** 으로만 설계 되었습니다.

더 현대적이 고 안전한 방법은 **Hashicorp Vault** 또는 **Azure Key Vault** 같은 비밀 관리 도구에서 비밀을 격리 하는 것입니다.  이러한 도구를 사용 하 여 암호를 외부에 저장 하 고, 환경 간에 자격 증명을 변경 하 고, 응용 프로그램 코드에서이를 참조 합니다 그러나 각 도구에는 복잡성과 학습 곡선이 있습니다.

D 4는 비밀 관리를 간소화 하는 빌딩 블록을 제공 합니다.

## <a name="what-it-solves"></a>해결 방법

Eapr [비밀 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/secrets/secrets-overview/) 은 비밀 및 비밀 관리 도구를 사용 하는 복잡 한 작업을 추상화 합니다.

- 통합 인터페이스를 통해 기본으로 표시 되는을 숨깁니다.
- 개발 및 프로덕션에 따라 달라질 수 있는 다양 한 *플러그형* 암호 저장소 구성 요소를 지원 합니다.
- 응용 프로그램에는 비밀 저장소 라이브러리에 대 한 직접 종속성이 필요 하지 않습니다.
- 개발자는 각 암호 저장소에 대 한 자세한 지식이 필요 하지 않습니다.

D 4는 위의 모든 문제를 처리 합니다.

비밀에 대 한 액세스는 인증 및 권한 부여를 통해 보안이 유지 됩니다. 충분 한 권한이 있는 응용 프로그램만 비밀에 액세스할 수 있습니다. Kubernetes에서 실행 되는 응용 프로그램은 기본 제공 암호 관리 메커니즘을 사용할 수도 있습니다.

## <a name="how-it-works"></a>작동 방식

응용 프로그램은 다음 두 가지 방법으로 암호 구성 요소를 사용 합니다.

- 응용 프로그램 블록에서 직접 암호를 검색 합니다.
- Eapr 구성 요소 구성에서 간접적으로 비밀을 참조 합니다.

비밀을 직접 검색 하는 방법은 먼저 설명 합니다. Eapr 구성 요소 구성 파일에서 암호를 참조 하는 것은 이후 섹션에서 다룹니다.

응용 프로그램은 암호 구성 요소를 사용할 때 사이드카와 상호 작용 합니다. 사이드카는 비밀 API를 노출 합니다. API는 HTTP 또는 gRPC를 사용 하 여 호출할 수 있습니다. 다음 URL을 사용 하 여 HTTP API를 호출 합니다.

```http
http://localhost:<dapr-port>/v1.0/secrets/<store-name>/<name>?<metadata>
```

URL에는 다음 세그먼트가 포함 됩니다.

- `<dapr-port>` 사이드카가 수신 대기 하는 포트 번호를 지정 합니다.
- `<store-name>` 은 (는) Eapr 비밀 저장소의 이름을 지정 합니다.
- `<name>` 검색할 암호의 이름을 지정 합니다.
- `<metadata>` 비밀에 대 한 추가 정보를 제공 합니다. 이 세그먼트는 선택 사항이 며 메타 데이터 속성은 암호 저장소 마다 다릅니다. 메타 데이터 속성에 대 한 자세한 내용은 [암호 API 참조]([Secrets API reference | Dapr Docs](https://docs.dapr.io/reference/api/secrets_api/))를 참조 하세요.

 > [!NOTE]
 > 위의 URL은 HTTP 또는 gRPC를 지 원하는 개발 플랫폼에서 사용할 수 있는 기본 Eapr API 호출을 나타냅니다. .NET, Java 및 Go와 같은 널리 사용 되는 플랫폼에는 고유한 사용자 지정 Api가 있습니다.

JSON 응답에는 암호의 키와 값이 포함 됩니다.

그림 10-1에서는이 암호 API에 대 한 요청을 처리 하는 방법을 보여 줍니다.

![Eapr 비밀 API를 사용 하 여 비밀을 검색 하는 다이어그램입니다.](media/secrets/secrets-flow.png)

**그림 10-1**. Eapr 비밀 API를 사용 하 여 암호 검색

1. 서비스는 암호 저장소의 이름 및 검색할 암호와 함께 Eapr 비밀 API를 호출 합니다.
1. 사이드카는 암호 저장소에서 지정 된 암호를 검색 합니다.
1. 사이드카는 비밀 정보를 서비스로 돌려 반환 합니다.

일부 비밀 저장소는 단일 비밀에 여러 키/값 쌍을 저장 하도록 지원 합니다. 이러한 시나리오의 경우 응답에는 다음 예제와 같이 단일 JSON 응답에 여러 키/값 쌍이 포함 됩니다.

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

또한 응용 프로그램에서 액세스할 수 있는 모든 암호를 검색 하는 작업을 제공 합니다.

```http
http://localhost:<dapr-port>/v1.0/secrets/<store-name>/bulk
```

## <a name="use-the-dapr-net-sdk"></a>Dapr .NET SDK 사용

.NET 개발자를 위해 Dapr .NET SDK는 Dapr 비밀 관리를 간소화 합니다. 메서드를 살펴보겠습니다 `DaprClient.GetSecretAsync` . 이 기능을 사용 하면 최소한의 노력으로 모든 Eapr 암호 저장소에서 직접 암호를 검색할 수 있습니다. SQL Server 데이터베이스에 대 한 연결 문자열 암호를 인출 하는 예는 다음과 같습니다.

```csharp
var metadata = new Dictionary<string, string> { ["version_id"] = "3" };
Dictionary<string, string> secrets = await daprClient.GetSecretAsync("secret-store", "eshopsecrets", metadata);
string connectionString = secrets["customerdb"];
```

메서드에 대 한 인수 `GetSecretAsync` 는 다음과 같습니다.

- Eapr 비밀 저장소 구성 요소의 이름 (' secret-store ')
- 검색할 암호 (' eshopsecrets ')입니다.
- 선택적 메타 데이터 키/값 쌍 (' version_id = 3 ')

비밀에 여러 키/값 쌍이 포함 될 수 있으므로 메서드는 사전 개체를 사용 하 여 응답 합니다. 위의 예제에서 라는 암호는 `customerdb` 연결 문자열을 반환 하기 위해 컬렉션에서 참조 됩니다.

Dapr .NET SDK는 .NET 구성 공급자도 갖추고 있습니다. 기본 [.Net Core 구성 API](../../core/extensions/configuration.md)에 지정 된 암호를 로드 합니다. 그러면 실행 중인 응용 프로그램이 `IConfiguration` ASP.NET Core 종속성 주입에 등록 된 사전에서 비밀을 참조할 수 있습니다.

비밀 구성 공급자는 [Dapr.Extensions.Configuration](https://www.nuget.org/packages/Dapr.Extensions.Configuration) NuGet 패키지에서 사용할 수 있습니다. 공급자는 `Program.cs` ASP.NET Web API 응용 프로그램의에 등록할 수 있습니다.  

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

위의 예제에서는 `eshopsecrets` 시작할 때 .net 구성 시스템에 비밀 컬렉션을 로드 합니다. 공급자를 등록 하려면 인스턴스를 사용 `DaprClient` 하 여 사이드카에서 암호 API를 호출 해야 합니다. 다른 인수에는 비밀 저장소의 이름과 암호의 이름을 포함 하는 개체가 포함 됩니다 `DaprSecretDescriptor` .

로드 되 면 응용 프로그램 코드에서 직접 암호를 검색할 수 있습니다.

```csharp
public void GetCustomer(IConfiguration config)
{
    var connectionString = config["eshopsecrets"]["customerdb"];
}
```

## <a name="secret-store-components"></a>비밀 저장소 구성 요소

비밀 빌딩 블록은 몇 가지 비밀 저장소 구성 요소를 지원 합니다. 작성 시 다음과 같은 비밀 저장소를 사용할 수 있습니다.

- 환경 변수
- 로컬 파일
- Kubernetes 비밀
- AWS 암호 관리자
- Azure Key Vault
- GCP 암호 관리자
- HashiCorp 자격 증명 모음

> [!IMPORTANT]
> 환경 변수와 로컬 파일 구성 요소는 개발 작업 전용으로 설계 되었습니다.

다음 섹션에서는 비밀 저장소를 구성 하는 방법을 보여 줍니다.

### <a name="configuration"></a>구성

Eapr 구성 요소 구성 파일을 사용 하 여 비밀 저장소를 구성 합니다. 파일의 일반적인 구조는 다음과 같습니다.

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

모든 Eapr 구성 요소 구성 파일에는 `name` 선택적 값과 함께가 필요 `namespace` 합니다. 또한 `type` 섹션의 필드는 `spec` 비밀 저장소 구성 요소의 유형을 지정 합니다. 섹션의 속성은 `metadata` 암호 저장소 마다 다릅니다.

### <a name="indirectly-consume-dapr-secrets"></a>매우 Apr 암호를 간접적으로 사용

이 챕터의 앞부분에서 설명한 것 처럼 응용 프로그램은 구성 요소 구성 파일에서 암호를 참조 하 여 사용할 수도 있습니다. 상태를 저장 하는 데 Redis cache를 사용 하는 [상태 관리 구성 요소](state-management.md) 를 고려 합니다.

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

위의 구성 파일에는 Redis 서버에 연결 하기 위한 **일반 텍스트** 암호가 포함 되어 있습니다. **하드 코드** 된 암호는 항상 잘못 된 개념입니다. 이 구성 파일을 공용 리포지토리로 푸시하여 암호를 노출 합니다. 암호를 비밀 저장소에 저장 하면이 시나리오를 크게 향상 시킬 수 있습니다.

다음 예제에서는 여러 가지 암호 저장소를 사용 하 여이를 보여 줍니다.

### <a name="local-file"></a>로컬 파일

로컬 파일 구성 요소는 개발 시나리오를 위해 설계 되었습니다. JSON 파일 내에서 로컬 파일 시스템에 대 한 암호를 저장 합니다. 다음은 라는 예제 `eshop-secrets.json` 입니다. Redis에 대 한 단일 암호 a 암호를 포함 합니다.

```json
{
  "eShopRedisPassword": "e$h0p0nD@pr"
}
```

이 파일 `components` 은 Eapr 응용 프로그램을 실행할 때 지정 하는 폴더에 저장 합니다.

다음 비밀 저장소 구성 파일은 JSON 파일을 비밀 저장소로 사용 합니다. 또한 폴더에 배치 됩니다 `components` .

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

구성 요소 `secretstore.local.file` 형식이 인 경우 `secretsFile`Metadata 요소는 비밀 파일의 경로를 지정 합니다.

> [!IMPORTANT]
> 비밀 파일의 경로는 절대 경로 또는 상대 경로일 수 있습니다. 상대 경로는 응용 프로그램이 시작 되는 폴더를 기반으로 합니다. 이 예제에서 폴더는 `components` .net 응용 프로그램이 포함 된 디렉터리의 하위 폴더입니다.

응용 프로그램 폴더에서 경로를 명령줄 인수로 지정 하 여 Eapr 응용 프로그램을 시작 합니다 `components` .

```console
dapr run --app-id basket-api --components-path ./components dotnet run
```

> [!NOTE]
> 위의 예제는 자체 호스팅 모드에서 실행 중인 경우에 적용 됩니다. Kubernetes 호스팅의 경우 볼륨 탑재를 사용 하는 것이 좋습니다.

`nestedSeparator`Eapr 구성 파일의는 JSON 계층 구조를 *평면화* 하는 문자를 지정 합니다. 다음 코드 조각을 살펴보십시오.

```json
{
    "redisPassword": "some password",
    "connectionStrings": {
        "customerdb": "some connection string",
        "productdb": "some connection string"
    }
}
```

콜론을 구분 기호로 사용 하 여 `customerdb` 키를 사용 하 여 연결 문자열을 검색할 수 있습니다 `connectionStrings:customerdb` .

> [!NOTE]
> 콜론은 `:` 기본 구분 기호 값입니다.

다음 예제에서 상태 관리 구성 파일은 로컬 암호 저장소 구성 요소를 참조 하 여 Redis 서버에 연결 하기 위한 암호를 가져옵니다.

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

`secretKeyRef`요소는 암호를 포함 하는 암호를 참조 합니다. 이전의 *일반 텍스트* 값을 대체 합니다. 비밀 이름 및 키 이름인는 비밀을 `eShopRedisPassword` 참조 합니다. 비밀 관리 구성 요소의 이름은 `eshop-local-secret-store` `auth` metadata 요소에 있습니다.

`eShopRedisPassword`암호 참조의 이름과 키에 대해가 동일한 이유를 궁금할 수 있습니다. 로컬 파일 비밀 저장소에서 비밀은 별도의 이름으로 식별 되지 않습니다. 시나리오는 다음 예제에서 Kubernetes 암호를 사용 하는 것과 다릅니다.

### <a name="kubernetes-secret"></a>Kubernetes 암호

이 두 번째 예제에서는 Kubernetes에서 실행 되는 4Apr 응용 프로그램을 중심으로 설명 합니다. Kubernetes에서 제공 하는 표준 비밀 메커니즘을 사용 합니다. Kubernetes CLI ()를 사용 `kubectl` 하 여 `eshop-redis-secret` 암호를 포함 하는 라는 암호를 만듭니다.

```console
kubectl create secret generic eshopsecrets --from-literal=redisPassword=e$h0p0nD@pr -n eshop
```

일단 만들어지면 상태 관리를 위해 구성 요소 구성 파일에서 암호를 참조할 수 있습니다.

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

`secretKeyRef`요소는 각각 Kubernetes 암호와 비밀 키, 및의 이름을 지정 합니다 `eshopsecrets` `redisPassword` . `auth`메타 데이터 섹션은 Kubernetes 암호 관리 구성 요소를 사용 하도록 d 4에 지시 합니다.

> [!NOTE]
> Kubernetes 암호를 사용 하는 경우에는 Auth가 기본값이 며 생략할 수 있습니다.

프로덕션 설정에서 비밀은 일반적으로 자동화 된 CI/CD 파이프라인의 일부로 생성 됩니다. 이렇게 하면 충분 한 권한이 있는 사용자만 암호에 액세스 하 고 변경할 수 있습니다. 개발자는 암호의 실제 값을 알지 못해도 구성 파일을 만듭니다.

### <a name="azure-key-vault"></a>Azure Key Vault

다음 예제는 실제 프로덕션 시나리오에 맞게 설계 되었습니다. 비밀 저장소로 **Azure Key Vault** 를 사용 합니다. Azure Key Vault는 암호를 클라우드에 안전 하 게 저장할 수 있게 해 주는 관리 되는 Azure 서비스입니다.

이 예제가 작동 하려면 다음 필수 구성 요소를 충족 해야 합니다.

- Azure 구독에 대 한 관리 액세스를 보호 했습니다.
- `eshopkv` `redisPassword` Redis 서버에 연결 하기 위한 암호를 포함 하는 라는 암호를 포함 하는 라는 Azure Key Vault를 프로 비전 했습니다.
- Azure Active Directory에서 [서비스 주체](/azure/active-directory/develop/howto-create-service-principal-portal) 를 만들었습니다.
- 로컬 파일 시스템에이 서비스 사용자에 대 한 X509 인증서 (공개 키와 개인 키 둘 다 포함)를 설치 했습니다.

> [!NOTE]
> 서비스 주체는 응용 프로그램에서 Azure 서비스를 인증 하는 데 사용할 수 있는 id입니다. 서비스 주체는 X509 인증서를 사용 합니다. 응용 프로그램은이 인증서를 자격 증명으로 사용 하 여 자신을 인증 합니다.

[Azure Key Vault 암호 저장소 설명서](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault/) 는 Key Vault 환경을 만들고 구성 하는 단계별 지침을 제공 합니다.

#### <a name="use-key-vault-when-running-in-self-hosted-mode"></a>자체 호스팅 모드로 실행 하는 경우 Key Vault 사용

다음 구성 파일을 사용 하 여 Eapr 자체 호스팅 모드에서 Azure Key Vault를 사용 해야 합니다.

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

비밀 저장소 `secretstores.azure.keyvault` 형식이 인 경우 `metadata`Key Vault에 대 한 액세스를 구성 하는 요소에는 다음 속성이 필요 합니다.

- 에는 `vaultName` Azure Key Vault 이름이 포함 됩니다.
- 에는 `spnTenantId` Key Vault에 대 한 인증에 사용 되는 서비스 사용자의 *테 넌 트 ID가* 포함 되어 있습니다.
- 에는 `spnClientId` Key Vault에 대 한 인증에 사용 되는 서비스 주체의 *앱 ID* 가 포함 되어 있습니다.
- 에는 `spnCertificateFile` 서비스 사용자가 Key Vault에 대해 인증할 인증서 파일에 대 한 경로가 포함 되어 있습니다.

> [!TIP]
> Azure Portal 또는 Azure CLI에서 서비스 사용자 정보를 복사할 수 있습니다.

이제 응용 프로그램은 Azure Key Vault에서 Redis 암호를 검색할 수 있습니다.

#### <a name="use-key-vault-when-running-on-kubernetes"></a>Kubernetes에서 실행 하는 경우 Key Vault 사용

Kubernetes와 함께 Azure Key Vault를 사용 하려면 Azure Key Vault에 대해 인증 하는 서비스 사용자도 필요 합니다.

먼저 kubectl CLI 도구를 사용 하 여 인증서 파일을 포함 하는 *Kubernetes 암호* 를 만듭니다.

```console
kubectl create secret generic [k8s_spn_secret_name] --from-file=[pfx_certificate_file_local_path] -n eshop
```

명령에는 다음 두 명령줄 인수가 필요 합니다.

- `[k8s_spn_secret_name]` Kubernetes secret store의 비밀 이름입니다.
- `[pfx_certificate_file_local_path]` X509 인증서 파일의 경로입니다.

일단 만들어지면 비밀 저장소 구성 요소 구성 파일에서 Kubernetes 암호를 참조할 수 있습니다.

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

이 시점에서 Kubernetes에서 실행 되는 응용 프로그램은 Azure Key Vault에서 Redis 암호를 검색할 수 있습니다.

> [!IMPORTANT]
> 서비스 사용자에 대 한 X509 인증서 파일을 안전한 장소에 보관 하는 것이 중요 합니다. 소스 코드 리포지토리 외부의 잘 알려진 폴더에 저장 하는 것이 가장 좋습니다. 구성 파일은이 잘 알려진 폴더에서 인증서 파일을 참조할 수 있습니다. 로컬 개발 컴퓨터에서는 인증서를 폴더에 복사 해야 합니다. 자동 배포의 경우 파이프라인이 응용 프로그램이 배포 된 컴퓨터에 인증서를 복사 합니다. 환경 마다 다른 서비스 주체를 사용 하는 것이 좋습니다. 이렇게 하면 개발 환경의 서비스 주체가 프로덕션 환경의 암호에 액세스할 수 없습니다.

Azure Kubernetes 서비스 (AKS)에서 실행 되는 경우 [Azure 관리 id](/azure/active-directory/managed-identities-azure-resources/overview) 를 사용 하 여 Azure Key Vault에 대 한 인증을 받는 것이 좋습니다. 관리 id는이 책의 범위를 벗어나지만 관리 되는 [id를 사용 하 여 Azure Key Vault](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault-managed-identity/) 설명서에 설명 되어 있습니다.

### <a name="scope-secrets"></a>범위 비밀

비밀 범위를 사용 하면 응용 프로그램에서 액세스할 수 있는 암호를 제어할 수 있습니다. Eapr 사이드카 구성 파일에서 범위를 구성 합니다. [Eapr 구성 설명서](https://docs.dapr.io/operations/configuration/configuration-overview/) 에서는 비밀 범위 지정을 위한 지침을 제공 합니다.

비밀 범위를 포함 하는 Eapr 사이드카 구성 파일의 예는 다음과 같습니다.

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

비밀 저장소 당 범위를 지정 합니다. 위의 예제에서 비밀 저장소의 이름은 `eshop-azurekv-secret-store` 입니다. 다음 속성을 사용 하 여 암호에 대 한 액세스를 구성 합니다.

| 속성         | 값               | 설명                                                                                                                       |
|------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| `defaultAccess`  | `allow` 또는 `deny`   | 지정 된 암호 저장소의 *모든* 암호에 대 한 액세스를 허용 하거나 거부 합니다. 이 속성은 선택 사항이 며 기본값은 `allow` 입니다. |
| `allowedSecrets` | 비밀 키 목록 | 배열에 지정 된 비밀에 액세스할 수 있습니다. 이 속성은 선택 사항입니다.                                                     |
| `deniedSecrets`  | 비밀 키 목록 | 배열에 지정 된 암호에는 액세스할 수 없습니다. 이 속성은 선택 사항입니다.                                                 |

`allowedSecrets`및 `deniedSecrets` 속성은 속성 보다 우선적으로 적용 `defaultAccess` 됩니다. 및 목록을 지정 한다고 가정 `defaultAccess: allowed` `allowedSecrets` 합니다. 이 경우 `allowedSecrets` 응용 프로그램에서 목록의 암호만 액세스할 수 있습니다.

## <a name="reference-application-eshopondapr"></a>참조 응용 프로그램: eShopOnDapr

EShopOnDapr reference 응용 프로그램은 두 비밀에 대해 암호 구성 요소를 사용 합니다.

- Redis cache에 연결 하기 위한 암호입니다.
- Twilio Sendgrid API를 사용 하기 위한 API 키입니다. 응용 프로그램은 Twillio를 사용 하 여 [바인딩 빌딩 블록 챕터](bindings.md)에 설명 된 것 처럼, eapr 출력 바인딩을 사용 하 여 전자 메일을 보냅니다.

Docker Compose를 사용 하 여 응용 프로그램을 실행 하는 경우 **로컬 파일** 비밀 저장소가 사용 됩니다. 구성 요소 구성 파일은 `eshop-secretstore.yaml` `dapr/components` eShopOnDapr 리포지토리의 폴더에 있습니다.

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

구성 파일은 `eshop-secretstore.json` 동일한 폴더에 있는 로컬 저장소 파일을 참조 합니다.

```json
{
    "redisPassword": "**********",
    "sendgridAPIKey": "**********"
}
```

폴더는 명령줄 `components` 에서 지정 되 고,이 폴더는 Eapr 사이드카 컨테이너 내의 로컬 폴더로 탑재 됩니다. `docker-compose.override.yml`볼륨 탑재를 지정 하는 리포지토리 루트에 있는 파일의 조각은 다음과 같습니다.

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
> Docker Compose 재정의 파일은 환경 특정 구성 값을 포함 합니다.

`/components`볼륨 탑재 및 `--components-path` 명령줄 인수는 시작 명령에 전달 됩니다 `daprd` .

구성 된 후에는 다른 구성 요소 구성 파일 에서도 암호를 참조할 수 있습니다. 비밀을 사용 하는 게시/구독 구성 요소 구성의 예는 다음과 같습니다.

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

위의 예제에서 로컬 Redis 저장소는 비밀을 참조 하는 데 사용 됩니다.

## <a name="summary"></a>요약

4Apr 비밀 빌딩 블록은 암호 및 연결 문자열과 같은 중요 한 구성 설정을 저장 하 고 검색 하는 기능을 제공 합니다. 비밀을 비공개로 유지 하 고 실수로 공개 되지 않도록 방지 합니다.

빌딩 블록은 다양 한 암호 저장소를 지원 하 고,이를 통해 복잡 한 암호를 만들 수 있습니다.

Dapr .NET SDK는 `DaprClient` 암호를 검색 하는 개체를 제공 합니다. 또한 .NET Core 구성 시스템에 암호를 추가 하는 .NET 구성 공급자를 포함 합니다. 로드 된 후에는 .NET 코드에서 이러한 암호를 사용할 수 있습니다.

비밀 범위를 사용 하 여 특정 비밀에 대 한 액세스를 제어할 수 있습니다.

## <a name="references"></a>참조

- [Twelve-Factor 응용 프로그램 외](https://tanzu.vmware.com/content/blog/beyond-the-twelve-factor-app)

>[!div class="step-by-step"]
>[이전](observability.md)
>[다음](summary.md)
