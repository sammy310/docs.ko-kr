---
title: Blazor앱 호스팅 모델
description: 또는 서버에서 브라우저를 포함 하 여 앱을 호스트 하는 여러 가지 방법을 알아봅니다 Blazor WebAssembly .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: a0d37392a65cfcbff9642476d9fdb1e5c662e66a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173265"
---
# <a name="blazor-app-hosting-models"></a>Blazor앱 호스팅 모델

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Blazor앱은 ASP.NET Web Forms apps와 마찬가지로 IIS에서 호스팅될 수 있습니다. Blazor다음 방법 중 하나로 앱을 호스팅할 수도 있습니다.

- 클라이언트 쪽의 브라우저에 WebAssembly 있습니다.
- ASP.NET Core 앱의 서버 쪽

## <a name="blazor-webassembly-apps"></a>BlazorWebAssembly앱

BlazorWebAssembly앱은 기반 .net 런타임의 브라우저에서 직접 실행 WebAssembly 됩니다. BlazorWebAssembly앱은 각도 또는 반응 처럼 프런트 엔드 JavaScript 프레임 워크와 비슷한 방식으로 작동 합니다. 그러나 JavaScript를 작성 하는 대신 c #을 작성 합니다. 앱 어셈블리 및 모든 필수 종속성과 함께 .NET 런타임이 앱과 함께 다운로드 됩니다. 브라우저 플러그 인 또는 확장이 필요 하지 않습니다.

다운로드 된 어셈블리는 다른 .NET 앱에서 사용 하는 것과 같은 일반적인 .NET 어셈블리입니다. 런타임에서는 .NET Standard을 지원 하기 때문에 기존 .NET Standard 라이브러리를 앱과 함께 사용할 수 있습니다 Blazor WebAssembly . 그러나 이러한 어셈블리는 여전히 브라우저 보안 샌드박스에서 실행 됩니다. 일부 기능은 <xref:System.PlatformNotSupportedException> 파일 시스템에 액세스 하거나 임의의 네트워크 연결을 여는 등의을 throw 할 수 있습니다.

앱이 로드 되 면 .NET 런타임이 시작 되 고 응용 프로그램 어셈블리를 가리킵니다. 앱 시작 논리가 실행 되 고 루트 구성 요소가 렌더링 됩니다. Blazor구성 요소의 렌더링 된 출력을 기반으로 UI 업데이트를 계산 합니다. 그러면 DOM 업데이트가 적용 됩니다.

![Blazor WebAssembly](media/hosting-models/blazor-webassembly.png)

BlazorWebAssembly앱은 전적으로 클라이언트 쪽을 실행 합니다. 이러한 앱은 GitHub 페이지 또는 Azure 정적 웹 사이트 호스팅 같은 정적 사이트 호스팅 솔루션에 배포할 수 있습니다. 서버에는 .NET이 필요 하지 않습니다. 앱의 일부에 대 한 심층 링크를 사용 하려면 일반적으로 서버에서 라우팅 솔루션이 필요 합니다. 라우팅 솔루션은 요청을 앱의 루트에 리디렉션합니다. 예를 들어 IIS에서 URL 다시 쓰기 규칙을 사용 하 여이 리디렉션을 처리할 수 있습니다.

Blazor및 전체 스택 .net 웹 개발의 모든 이점을 얻으려면 Blazor WebAssembly ASP.NET Core으로 앱을 호스팅합니다. 클라이언트와 서버 모두에서 .NET을 사용 하면 일관 된 언어, 프레임 워크 및 도구 집합을 사용 하 여 코드를 쉽게 공유 하 고 앱을 빌드할 수 있습니다. BlazorBlazor앱과 ASP.NET Core 호스트 프로젝트를 모두 포함 하는 솔루션을 설정 하기 위한 편리한 템플릿을 제공 WebAssembly 합니다. 솔루션이 빌드될 때 앱에서 빌드된 정적 파일은 Blazor 대체 라우팅이 이미 설정 된 ASP.NET Core 앱에서 호스팅됩니다.

## <a name="blazor-server-apps"></a>Blazor서버 앱

[ Blazor 아키텍처](architecture-comparison.md#blazor) 에 Blazor 대 한 설명은 구성 요소가 이라는 중간 추상화로 출력을 렌더링 `RenderTree` 합니다. Blazor그런 다음 프레임 워크는 이전에 렌더링 된 항목을 사용 하 여 렌더링 된 항목을 비교 합니다. 차이점은 DOM에 적용 됩니다. Blazor구성 요소는 렌더링 된 출력이 적용 되는 방식에서 분리 됩니다. 따라서 구성 요소 자체는 UI를 업데이트 하는 프로세스와 동일한 프로세스에서 실행할 필요가 없습니다. 실제로 동일한 컴퓨터에서 실행 해야 하는 것은 아닙니다.

Blazor서버 앱에서 구성 요소는 브라우저에서 클라이언트 쪽이 아닌 서버에서 실행 됩니다. 브라우저에서 발생 하는 UI 이벤트는 실시간 연결을 통해 서버에 전송 됩니다. 이벤트는 올바른 구성 요소 인스턴스로 디스패치 됩니다. 구성 요소가 렌더링 되 고, 계산 된 UI 차이는 serialize 되어 DOM에 적용 되는 브라우저에 전송 됩니다.

![Blazor서버인](media/hosting-models/blazor-server.png)

BlazorASP.NET AJAX 및 컨트롤을 사용 하는 경우 서버 호스팅 모델이 익숙할 수 있습니다 <xref:System.Web.UI.UpdatePanel> . `UpdatePanel`컨트롤은 페이지의 트리거 이벤트에 대 한 응답으로 부분 페이지 업데이트 적용을 처리 합니다. 트리거된 경우은 `UpdatePanel` 부분 업데이트를 요청한 다음 페이지를 새로 고칠 필요 없이 적용 합니다. UI 상태는를 사용 하 여 관리 됩니다 `ViewState` . Blazor서버 앱은 응용 프로그램에 클라이언트와의 활성 연결이 필요 하다는 차이가 있습니다. 또한 모든 UI 상태가 서버에서 유지 관리 됩니다. 이러한 차이를 제외 하 고 두 모델은 개념적으로 유사 합니다.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>올바른 호스팅 모델을 선택 하는 방법 Blazor

[ Blazor 호스팅 모델 문서](/aspnet/core/blazor/hosting-models)에 설명 된 대로 서로 다른 Blazor 호스팅 모델은 서로 다른 장단점을 갖습니다.

Blazor WebAssembly 호스팅 모델에는 다음과 같은 이점이 있습니다.

- .NET 서버 쪽 종속성이 없습니다. 클라이언트에 다운로드 한 후 앱이 완전히 작동 합니다.
- 클라이언트 리소스와 기능은 완전히 이용됩니다.
- 작업이 서버에서 클라이언트로 오프로드됩니다.
- 앱을 호스트하는 데 ASP.NET Core 웹 서버가 필요하지 않습니다. 서버리스 배포 시나리오가 가능합니다(예: CDN에서 앱 제공).

호스팅 모델의 단점이은 Blazor WebAssembly 다음과 같습니다.

- 브라우저 기능은 앱을 제한 합니다.
- 지원 되는 클라이언트 하드웨어 및 소프트웨어 (예: WebAssembly 지원)는 필수입니다.
- 다운로드 크기가 더 크고 앱 로드 시간이 더 깁니다.
- .NET 런타임 및 도구 지원의 완성도가 더 낮습니다. 예를 들어 [.NET Standard](../../standard/net-standard.md) 지원 및 디버깅에는 제한이 있습니다.

반대로 Blazor 서버 호스팅 모델은 다음과 같은 이점을 제공 합니다.

- 다운로드 크기는 클라이언트 쪽 앱 보다 훨씬 더 작기 때문에 앱이 훨씬 빠르게 로드 됩니다.
- 앱은 .NET Core와 호환 되는 Api의 사용을 포함 하 여 서버 기능을 최대한 활용 합니다.
- 서버의 .NET Core가 앱을 실행하는 데 사용되므로 디버깅과 같은 기존 .NET 도구가 정상적으로 작동합니다.
- 씬 클라이언트가 지원됩니다. 예를 들어 서버 쪽 앱은 WebAssembly 리소스 제한 장치에서 및를 지원 하지 않는 브라우저에서 작동 합니다.
- 앱 구성 요소 코드를 비롯한 앱의 .NET/C# 코드베이스가 클라이언트에 제공되지 않습니다.

서버 호스팅 모델에 대 한 단점이는 Blazor 다음과 같습니다.

- UI 대기 시간이 더 빠릅니다. 모든 사용자 조작에 네트워크 홉이 포함됩니다.
- 오프라인 지원이 없습니다. 클라이언트 연결에 실패하면 앱 작동이 중단됩니다.
- 여러 사용자가 있는 앱의 경우 확장성 구현이 어렵습니다. 서버에서 여러 개의 클라이언트 연결을 관리하고 클라이언트 상태를 처리해야 합니다.
- 앱을 제공하려면 ASP.NET Core 서버가 필요합니다. 서버를 사용 하지 않는 배포 시나리오는 불가능 합니다. 예를 들어 CDN에서 앱을 제공할 수 없습니다.

위의 장단점은 어려울 수 있지만 나중에 호스팅 모델을 변경할 수 있습니다. Blazor선택한 호스팅 모델에 관계 없이 구성 요소 모델은 *동일*합니다. 원칙적으로 동일한 구성 요소를 두 호스팅 모델에 모두 사용할 수 있습니다. 앱 코드는 변경 되지 않습니다. 그러나 구성 요소가 모델을 독립적으로 호스팅 상태로 유지 되도록 추상화를 도입 하는 것이 좋습니다. 추상화를 사용 하면 앱에서 다른 호스팅 모델을 보다 쉽게 채택할 수 있습니다.

## <a name="deploy-your-app"></a>앱 배포

ASP.NET Web Forms 앱은 일반적으로 Windows Server 컴퓨터 또는 클러스터의 IIS에서 호스팅됩니다. Blazor앱은 다음을 수행할 수도 있습니다.

- 정적 파일 또는 ASP.NET Core 앱으로 IIS에서 호스팅되어야 합니다.
- ASP.NET Core의 유연성을 활용 하 여 다양 한 플랫폼 및 서버 인프라에서 호스트할 수 있습니다. 예를 들어 Blazor Linux에서 [Nginx](/aspnet/core/host-and-deploy/linux-nginx) 또는 [Apache](/aspnet/core/host-and-deploy/linux-apache) 를 사용 하 여 앱을 호스트할 수 있습니다. 앱을 게시 하 고 배포 하는 방법에 대 한 자세한 내용은 Blazor Blazor [호스팅 및 배포](/aspnet/core/host-and-deploy/blazor/) 설명서를 참조 하세요.

다음 섹션에서는 Blazor WebAssembly 및 서버 앱에 대 한 프로젝트를 설정 하는 방법을 살펴보겠습니다 Blazor .

>[!div class="step-by-step"]
>[이전](architecture-comparison.md)
>[다음](project-structure.md)
