---
title: Azure 개발 프로세스
description: ASP.NET Core 및 Azure를 사용하여 최신 웹 애플리케이션 설계 | Azure 개발 프로세스
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 8907c63f8dcd57ec22c3c196cbb1db52d91a3b5f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/29/2020
ms.locfileid: "91169039"
---
# <a name="development-process-for-azure"></a>Azure 개발 프로세스

> _"클라우드를 사용하면 개인과 소규모 기업은 손가락만으로 엔터프라이즈급 서비스를 즉시 설정할 수 있습니다."_  
> _- Roy Stephan_

## <a name="vision"></a>비전

> *Visual Studio 또는 dotnet CLI와 Visual Studio Code 또는 원하는 편집기를 사용하여 원하는 방식으로 잘 설계된 ASP.NET Core 애플리케이션을 개발합니다.*

## <a name="development-environment-for-aspnet-core-apps"></a>ASP.NET Core 앱 개발 환경

### <a name="development-tools-choices-ide-or-editor"></a>개발 도구 선택: IDE 또는 편집기

개발자가 완전하고 강력한 IDE를 선호하든 아니면 가볍고 민첩한 편집기를 선호하든, Microsoft에서는 ASP.NET Core 애플리케이션 개발에 필요한 모든 것을 제공해 드립니다.

**Visual Studio 2019.** Visual Studio 2019는 ASP.NET Core용 애플리케이션을 개발하기 위한 동급 최고의 IDE입니다. 개발자의 생산성을 향상시키는 다양한 기능을 제공합니다. 이를 사용하여 애플리케이션을 개발하고 성능 및 기타 특성을 분석할 수 있습니다. 통합 디버거를 사용하면 코드 실행을 일시 중지하고 코드를 실행하면서 즉석에서 전후 단계로 이동할 수 있습니다. 기본 제공 테스트 실행기를 사용하면 테스트와 해당 결과를 구성할 수 있고 코딩하는 동안 라이브 유닛 테스트를 수행할 수도 있습니다. Live Share를 사용하면 다른 개발자와 실시간으로 공동 작업하여 네트워크를 통해 코드 세션을 원활하게 공유할 수 있습니다. 준비가 되면 Visual Studio에는 애플리케이션을 Azure 또는 원하는 호스트에 게시하는 데 필요한 모든 항목이 포함되어 있습니다.

[Visual Studio 2019 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

**Visual Studio Code 및 dotnet CLI**(Mac, Linux 및 Windows용 플랫폼 간 도구). 모든 개발 언어를 지원하는 가벼운 플랫폼 간 편집기를 선호하는 경우 Microsoft Visual Studio Code 및 docker CLI를 사용하면 됩니다. 이러한 제품은 간단하지만 강력한 환경을 제공하여 개발자 워크플로를 간소화합니다. 또한 Visual Studio Code는 C\# 확장 및 웹 개발을 지원하며, 편집기 내에서 인텔리전스 및 바로 가기 작업을 제공합니다.

[.NET Core SDK 다운로드](https://dotnet.microsoft.com/download)

[Visual Studio Code 다운로드](https://code.visualstudio.com/download)

## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Azure에서 호스트되는 ASP.NET Core 앱의 개발 워크플로

애플리케이션 개발 수명 주기는 각 개발자의 컴퓨터에서 시작되며, 개발자는 선호하는 언어를 사용하여 로컬로 앱을 코딩하고 테스트합니다. 개발자는 빌드 서버를 사용하여 또는 기본 제공 Azure 기능을 기반으로 선호하는 소스 제어 시스템을 선택하고 CI(연속 통합) 및/또는 CD(지속적인 업데이트/지속적인 배포)를 선택할 수 있습니다.

CI/CD를 사용하여 ASP.NET Core 애플리케이션 개발을 시작하려면 Azure DevOps Services 또는 조직에서 소유한 TFS(Team Foundation Server)를 사용하면 됩니다.

### <a name="initial-setup"></a>초기 설정

앱에 대한 릴리스 파이프라인을 만들려면 소스 제어에 애플리케이션 코드가 있어야 합니다. 로컬 리포지토리를 설정하고 팀 프로젝트의 원격 리포지토리에 연결합니다. 다음 지침을 따릅니다.

- [Git 및 Visual Studio와 코드 공유](/azure/devops/git/share-your-code-in-git-vs) 또는

- [TFVC 및 Visual Studio와 코드 공유](/azure/devops/tfvc/share-your-code-in-tfvc-vs)

애플리케이션을 배포할 Azure App Service를 만듭니다. Azure Portal에서 App Services 블레이드로 이동하여 웹앱을 만듭니다. +추가를 클릭하고, 웹앱 템플릿을 선택하고, 만들기를 클릭하고, 이름과 기타 세부 정보를 입력합니다. 웹앱은 {name}.azurewebsites.net에서 액세스할 수 있습니다.

![AzureWebApp](./media/image10-2.png)

**그림 10-1.** Azure Portal에서 새 Azure App Service 웹앱을 만듭니다.

CI 빌드 프로세스는 프로젝트의 소스 제어 리포지토리에 새 코드가 커밋될 때마다 자동화된 빌드를 수행합니다. 이렇게 하면 코드에서 빌드하고(그리고 이상적으로 자동화된 테스트를 전달하고) 잠재적으로 배포할 수 있습니다. 이 CI 빌드는 웹 배포 패키지 아티팩트를 생성하고 CD 프로세스에서 사용할 수 있도록 게시합니다.

[CI 빌드 프로세스 정의](/azure/devops/pipelines/ecosystems/dotnet-core)

팀원 중 누군가가 새 코드를 커밋할 때마다 시스템이 빌드를 대기열에 추가하도록 연속 통합을 사용해야 합니다. 빌드가 아티팩트 중 하나로 웹 배포 패키지를 생성하는지 빌드를 테스트 및 확인합니다.

빌드에 성공하면 CD 프로세스에서 CI 빌드 결과를 Azure 웹앱에 배포합니다. 이렇게 구성하려면 Azure App Service에 배포하는 *릴리스* 를 만들고 구성합니다.

[Azure 웹앱 배포](/azure/devops/pipelines/targets/webapp)

CI/CD 파이프라인이 구성되면 간단하게 웹앱을 업데이트하고 소스 제어에 커밋하여 배포할 수 있습니다.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Azure에서 호스트되는 ASP.NET Core 애플리케이션을 개발하는 워크플로

Azure 계정 및 CI/CD 프로세스 구성이 완료되면 Azure에서 호스트되는 ASP.NET Core 애플리케이션을 간단하게 개발할 수 있습니다. 다음은 그림 10-2처럼 Azure App Service에 웹앱으로 호스트되는 ASP.NET Core 앱을 빌드할 때 수행하는 기본 단계입니다.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**그림 10-2.** ASP.NET Core 앱을 빌드하고 Azure에서 호스팅하기 위한 단계별 워크플로

#### <a name="step-1-local-dev-environment-inner-loop"></a>1단계: 로컬 개발 환경 내부 루프

Azure에 배포할 ASP.NET Core 애플리케이션 개발은 일반적인 애플리케이션 개발과 다르지 않습니다. Visual Studio 2017, dotnet CLI, Visual Studio Code 또는 원하는 편집기 중 자신에게 편한 로컬 개발 환경을 사용하시면 됩니다. 코드를 작성하고, 변경 내용을 실행 및 디버그하고, 자동화된 테스트를 실행하고, 변경 내용을 공유 소스 제어 리포지토리에 푸시할 준비가 완료될 때까지 소스 제어에 로컬로 커밋할 수 있습니다.

#### <a name="step-2-application-code-repository"></a>2단계. 애플리케이션 코드 리포지토리

코드를 팀과 공유할 준비가 완료되면 로컬 소스 리포지토리의 변경 내용을 팀의 공유 소스 리포지토리에 푸시해야 합니다. 사용자 지정 분기에서 작업한 경우 이 단계에서 일반적으로 코드를 공유 분기에 병합(아마도 [끌어오기 요청](/azure/devops/git/pull-requests)을 사용하여)하는 작업이 포함됩니다.

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>3단계. 빌드 서버: 지속적인 통합 빌드, 테스트, 패키지

공유 애플리케이션 코드 리포지토리에 새 커밋이 만들어질 때마다 빌드 서버에서 새 빌드가 트리거됩니다. CI 프로세스의 일환으로, 이 빌드는 애플리케이션을 완전히 컴파일하고 자동화된 테스트를 실행하여 모든 것이 예상대로 작동하는지 확인해야 합니다. CI 프로세스의 최종 결과는 즉시 배포가 가능한 웹앱의 패키지 버전이어야 합니다.

#### <a name="step-4-build-server-continuous-delivery"></a>4단계. 빌드 서버: 지속적인 업데이트

빌드가 성공하면 CD 프로세스에서는 생성된 빌드 아티팩트를 선택합니다. 여기에는 웹 배포 패키지가 포함됩니다. 빌드 서버는 이 패키지를 Azure App Service에 배포하여 기존 서비스를 새로 만든 서비스로 바꿉니다. 일반적으로 이 단계는 스테이징 환경을 대상으로 하지만, 일부 애플리케이션은 CD 프로세스를 통해 프로덕션 환경에 직접 배포합니다.

#### <a name="step-5-azure-app-service-web-app"></a>5단계. Azure App Service 웹앱

배포되면 ASP.NET Core 애플리케이션은 Azure App Service 웹앱의 컨텍스트 내에서 실행됩니다. 이 웹앱은 Azure Portal을 사용하여 모니터링하고 추가로 구성할 수 있습니다.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>6단계. 프로덕션 모니터링 및 진단

웹앱이 실행되는 동안 애플리케이션의 상태를 모니터링하고 진단 및 사용자 동작 데이터를 수집할 수 있습니다. Application Insights는 Visual Studio에 포함되어 있으며, ASP.NET 앱을 위한 자동 계측 기능을 제공합니다. 사용량, 예외, 요청, 성능 및 로그에 대한 정보를 제공할 수 있습니다.

## <a name="references"></a>참조 항목

**ASP.NET Core 앱을 빌드하고 Azure에 배포**  
<https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core>

>[!div class="step-by-step"]
>[이전](test-asp-net-core-mvc-apps.md)
>[다음](azure-hosting-recommendations-for-asp-net-web-apps.md)
