---
title: Blazor 앱 호스팅 모델
description: Blazor 앱을 호스트 하는 다양 한 방법에 대해 알아봅니다 .이는 서버에서 Weasembmbsembmba를 포함 합니다.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 5bf55fa686691acc25508d3d9a6dfaf8aca321ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841950"
---
# <a name="blazor-app-hosting-models"></a>Blazor 앱 호스팅 모델

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Blazor apps는 ASP.NET Web Forms apps와 마찬가지로 IIS에서 호스팅될 수 있습니다. Blazor apps는 다음 중 한 가지 방법으로 호스트 될 수도 있습니다.

- 클라이언트 쪽에서의 브라우저에 있습니다.
- ASP.NET Core 앱의 서버 쪽

## <a name="blazor-webassembly-apps"></a>Blazor Weasembomapps

Blazor weasembomapps는 weasembmbombased 기반 .NET 런타임의 브라우저에서 직접 실행 됩니다. Blazor Weasembomapps는 각도 또는 반응 등의 프런트 엔드 JavaScript 프레임 워크와 비슷한 방식으로 작동 합니다. 그러나 JavaScript를 작성 하는 대신 작성 C#합니다. 앱 어셈블리 및 모든 필수 종속성과 함께 .NET 런타임이 앱과 함께 다운로드 됩니다. 브라우저 플러그 인 또는 확장이 필요 하지 않습니다.

다운로드 된 어셈블리는 다른 .NET 앱에서 사용 하는 것과 같은 일반적인 .NET 어셈블리입니다. 런타임에서 .NET Standard를 지원 하기 때문에 기존 .NET Standard 라이브러리를 Blazor Weasembomapp과 함께 사용할 수 있습니다. 그러나 이러한 어셈블리는 여전히 브라우저 보안 샌드박스에서 실행 됩니다. 일부 기능은 파일 시스템에 액세스 하거나 임의의 네트워크 연결을 여는 등의 <xref:System.PlatformNotSupportedException>을 throw 할 수 있습니다.

앱이 로드 되 면 .NET 런타임이 시작 되 고 응용 프로그램 어셈블리를 가리킵니다. 앱 시작 논리가 실행 되 고 루트 구성 요소가 렌더링 됩니다. Blazor는 구성 요소에서 렌더링 된 출력을 기반으로 UI 업데이트를 계산 합니다. 그러면 DOM 업데이트가 적용 됩니다.

![Blazor WebAssembly](media/hosting-models/blazor-webassembly.png)

Blazor Weasembomapps는 전적으로 클라이언트 쪽을 실행 합니다. 이러한 앱은 GitHub 페이지 또는 Azure 정적 웹 사이트 호스팅 같은 정적 사이트 호스팅 솔루션에 배포할 수 있습니다. 서버에는 .NET이 필요 하지 않습니다. 앱의 일부에 대 한 심층 링크를 사용 하려면 일반적으로 서버에서 라우팅 솔루션이 필요 합니다. 라우팅 솔루션은 요청을 앱의 루트에 리디렉션합니다. 예를 들어 IIS에서 URL 다시 쓰기 규칙을 사용 하 여이 리디렉션을 처리할 수 있습니다.

Blazor 및 전체 스택 .NET 웹 개발의 모든 이점을 얻으려면 ASP.NET Core를 사용 하 여 Blazor Weasembomapps를 호스팅합니다. 클라이언트와 서버 모두에서 .NET을 사용 하면 일관 된 언어, 프레임 워크 및 도구 집합을 사용 하 여 코드를 쉽게 공유 하 고 앱을 빌드할 수 있습니다. Blazor는 Blazor Weasembomapp 및 ASP.NET Core 호스트 프로젝트를 모두 포함 하는 솔루션을 설정 하기 위한 편리한 템플릿을 제공 합니다. 솔루션이 빌드될 때 Blazor 앱에서 빌드된 정적 파일은 대체 라우팅이 이미 설정 된 ASP.NET Core 앱에서 호스팅됩니다.

## <a name="blazor-server-apps"></a>Blazor 서버 앱

[Blazor 아키텍처](architecture-comparison.md#blazor) 토론에서 Blazor 구성 요소는 `RenderTree`라는 중간 추상화에 해당 출력을 렌더링 한다는 것을 기억 하세요. 그런 다음 Blazor 프레임 워크는 이전에 렌더링 된 항목을 사용 하 여 렌더링 된 항목을 비교 합니다. 차이점은 DOM에 적용 됩니다. Blazor 구성 요소는 렌더링 된 출력이 적용 되는 방식에서 분리 됩니다. 따라서 구성 요소 자체는 UI를 업데이트 하는 프로세스와 동일한 프로세스에서 실행할 필요가 없습니다. 실제로 동일한 컴퓨터에서 실행 해야 하는 것은 아닙니다.

Blazor Server 앱에서 구성 요소는 브라우저에서 클라이언트 쪽이 아닌 서버에서 실행 됩니다. 브라우저에서 발생 하는 UI 이벤트는 실시간 연결을 통해 서버에 전송 됩니다. 이벤트는 올바른 구성 요소 인스턴스로 디스패치 됩니다. 구성 요소가 렌더링 되 고, 계산 된 UI 차이는 serialize 되어 DOM에 적용 되는 브라우저에 전송 됩니다.

![Blazor 서버](media/hosting-models/blazor-server.png)

Blazor 서버 호스팅 모델은 ASP.NET AJAX 및 <xref:System.Web.UI.UpdatePanel> 컨트롤을 사용한 경우 익숙할 수 있습니다. `UpdatePanel` 컨트롤은 페이지의 트리거 이벤트에 대 한 응답으로 부분 페이지 업데이트를 적용 하는 것을 처리 합니다. 트리거된 경우 `UpdatePanel`은 부분 업데이트를 요청한 후 페이지를 새로 고칠 필요 없이 적용 합니다. UI 상태는 `ViewState`을 사용 하 여 관리 됩니다. Blazor 서버 앱은 클라이언트와의 활성 연결이 필요한 앱과 약간 다릅니다. 또한 모든 UI 상태가 서버에서 유지 관리 됩니다. 이러한 차이를 제외 하 고 두 모델은 개념적으로 유사 합니다.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Right Blazor 호스팅 모델을 선택 하는 방법

[Blazor 호스팅 모델 문서](https://docs.microsoft.com/aspnet/core/blazor/hosting-models#server-side)에 설명 된 대로 다른 Blazor 호스팅 모델은 서로 다른 장단점을 갖습니다.

Blazor Weasembom호스팅 모델에는 다음과 같은 이점이 있습니다.

- .NET 서버 쪽 종속성이 없습니다. 클라이언트에 다운로드 한 후 앱이 완전히 작동 합니다.
- 클라이언트 리소스 및 기능은 완전히 활용 됩니다.
- 작업은 서버에서 클라이언트로 오프 로드 됩니다.
- ASP.NET Core 웹 서버는 앱을 호스트 하는 데 필요 하지 않습니다. 서버를 사용 하지 않는 배포 시나리오를 사용할 수 있습니다. 예를 들어 CDN에서 앱을 제공할 수 있습니다.

Blazor Weasembom호스팅 모델의 단점이은 다음과 같습니다.

- 브라우저 기능은 앱을 제한 합니다.
- 가능 클라이언트 하드웨어 및 소프트웨어 (예: Weasembomsupport)는 필수입니다.
- 다운로드 크기가 크고 앱을 로드 하는 데 시간이 오래 걸립니다.
- .NET 런타임 및 도구 지원의 완성도는 낮아집니다. 예를 들어 [.NET Standard](../../standard/net-standard.md) 지원 및 디버깅에는 제한이 있습니다.

반대로 Blazor 서버 호스팅 모델은 다음과 같은 이점을 제공 합니다.

- 다운로드 크기는 클라이언트 쪽 앱 보다 훨씬 더 작기 때문에 앱이 훨씬 빠르게 로드 됩니다.
- 앱은 .NET Core와 호환 되는 Api의 사용을 포함 하 여 서버 기능을 최대한 활용 합니다.
- 서버의 .NET Core는 앱을 실행 하는 데 사용 되므로 디버깅과 같은 기존 .NET 도구는 정상적으로 작동 합니다.
- 씬 클라이언트가 지원 됩니다. 예를 들어 서버 쪽 앱은 리소스 제한 장치에서 Weasembmbambmbsemba를 지원 하지 않는 브라우저에서 작동 합니다.
- 앱의 구성 요소 코드C# 를 포함 하 여 앱의 .net/code 베이스가 클라이언트에 제공 되지 않습니다.

Blazor 서버 호스팅 모델에 대 한 단점이는 다음과 같습니다.

- UI 대기 시간이 더 빠릅니다. 모든 사용자 상호 작용에는 네트워크 홉이 포함 됩니다.
- 오프 라인은 지원 되지 않습니다. 클라이언트 연결에 실패 하면 앱 작동이 중지 됩니다.
- 여러 사용자가 있는 앱의 경우에는 확장성이 어렵습니다. 서버는 여러 클라이언트 연결을 관리 하 고 클라이언트 상태를 처리 해야 합니다.
- 앱을 제공 하려면 ASP.NET Core 서버가 필요 합니다. 서버를 사용 하지 않는 배포 시나리오는 불가능 합니다. 예를 들어 CDN에서 앱을 제공할 수 없습니다.

위의 장단점은 어려울 수 있지만 나중에 호스팅 모델을 변경할 수 있습니다. 선택 된 Blazor 호스팅 모델에 관계 없이 구성 요소 모델은 *동일*합니다. 원칙적으로 동일한 구성 요소를 두 호스팅 모델에 모두 사용할 수 있습니다. 앱 코드는 변경 되지 않습니다. 그러나 구성 요소가 모델을 독립적으로 호스팅 상태로 유지 되도록 추상화를 도입 하는 것이 좋습니다. 추상화를 사용 하면 앱에서 다른 호스팅 모델을 보다 쉽게 채택할 수 있습니다.

## <a name="deploy-your-app"></a>앱 배포

ASP.NET Web Forms 앱은 일반적으로 Windows Server 컴퓨터 또는 클러스터의 IIS에서 호스팅됩니다. Blazor apps도 다음을 수행할 수 있습니다.

- 정적 파일 또는 ASP.NET Core 앱으로 IIS에서 호스팅되어야 합니다.
- ASP.NET Core의 유연성을 활용 하 여 다양 한 플랫폼 및 서버 인프라에서 호스트할 수 있습니다. 예를 들어 Linux에서 [Nginx](/aspnet/core/host-and-deploy/linux-nginx) 또는 [Apache](/aspnet/core/host-and-deploy/linux-apache) 를 사용 하 여 Blazor 앱을 호스트할 수 있습니다. Blazor apps를 게시 하 고 배포 하는 방법에 대 한 자세한 내용은 Blazor [호스팅 및 배포](/aspnet/core/host-and-deploy/blazor/) 설명서를 참조 하세요.

다음 섹션에서는 Blazor We\sembmboma 및 Blazor Server 앱에 대 한 프로젝트를 설정 하는 방법을 살펴보겠습니다.

>[!div class="step-by-step"]
>[이전](architecture-comparison.md)
>[다음](project-structure.md)
