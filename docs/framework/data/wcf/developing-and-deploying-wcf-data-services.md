---
title: WCF Data Services 개발 및 배포
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: 4591175da5078a194bfe69884701e5432a0c38a3
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389736"
---
# <a name="develop-and-deploy-wcf-data-services"></a>WCF 데이터 서비스 개발 및 배포

이 문서에서는 WCF 데이터 서비스 개발 및 배포에 대한 정보를 제공합니다. WCF 데이터 서비스에 대한 자세한 내용은 [시작 및](getting-started-with-wcf-data-services.md) [개요를](wcf-data-services-overview.md)참조하십시오.

## <a name="develop-wcf-data-services"></a>WCF 데이터 서비스 개발

WCF 데이터 서비스를 사용하여 OData(개방형 데이터 프로토콜)를 지원하는 데이터 서비스를 만드는 경우 개발 중에 다음과 같은 기본 작업을 수행해야 합니다.

1. **데이터 모델 정의**

     WCF Data Services는 관계형 데이터베이스에서 라시 바인딩된 데이터 형식에 이르기까지 다양한 데이터 원본의 데이터를 기반으로 데이터 모델을 정의할 수 있는 다양한 데이터 서비스 공급자를 지원합니다. 자세한 내용은 [데이터 서비스 공급자](data-services-providers-wcf-data-services.md)합니다.

2. **데이터 서비스 만들기**

     가장 기본적인 데이터 서비스는 <xref:System.Data.Services.DataService%601> 클래스에서 상속하는 클래스를 엔터티 컨테이너의 네임스페이스로 정규화된 이름인 `T` 형식으로 노출합니다. 자세한 내용은 [Defining WCF Data Services](defining-wcf-data-services.md)의 개발 및 배포에 대한 정보를 제공합니다.

3. **데이터 서비스 구성**

     기본적으로 WCF 데이터 서비스는 엔터티 컨테이너에 의해 노출되는 리소스에 대한 액세스를 비활성화합니다. 인터페이스를 <xref:System.Data.Services.DataServiceConfiguration> 사용하면 리소스 및 서비스 작업에 대한 액세스를 구성하고, 지원되는 버전의 OData를 지정하고, 일괄 처리 동작 또는 단일 응답 피드에서 반환할 수 있는 최대 엔터티 수와 같은 다른 서비스 차원의 동작을 정의할 수 있습니다. 자세한 내용은 [데이터 서비스 구성](configuring-the-data-service-wcf-data-services.md)합니다.

이 문서에서는 주로 Visual Studio를 사용하여 데이터 서비스의 개발 및 배포를 다룹니다. OData 피드로 데이터를 노출하기 위해 WCF 데이터 서비스에서 제공하는 유연성에 대한 자세한 내용은 [WCF 데이터 서비스 정의를](defining-wcf-data-services.md)참조하십시오.

### <a name="choose-a-development-web-server"></a>개발 웹 서버 선택

Visual Studio 2015를 사용하여 WCF 데이터 서비스를 ASP.NET 응용 프로그램 또는 웹 사이트 ASP.NET 개발하는 경우 개발 중에 데이터 서비스를 실행할 웹 서버를 선택할 수 있습니다. 다음 웹 서버는 Visual Studio와 통합되어 로컬 컴퓨터에서 데이터 서비스를 보다 쉽게 테스트하고 디버깅할 수 있습니다.

1. **로컬 IIS 서버**

     인터넷 정보 서비스(IIS)에서 실행되는 ASP.NET 응용 프로그램 또는 ASP.NET 웹 사이트인 데이터 서비스를 만들 때 로컬 컴퓨터에서 IIS를 사용하여 데이터 서비스를 개발하고 테스트하는 것이 좋습니다. IIS에서 데이터 서비스를 실행하면 디버깅하는 동안 HTTP 요청을 쉽게 추적할 수 있습니다. 또한 IIS에서 데이터 서비스에 필요한 파일, 데이터베이스 및 기타 리소스에 액세스하는 데 필요한 권한을 미리 결정할 수도 있습니다. IIS에서 데이터 서비스를 실행하려면 IIS와 WCF(Windows 통신 재단)를 올바르게 설치하고 구성하고 파일 시스템 및 데이터베이스의 IIS 계정에 대한 액세스 권한을 부여해야 합니다. 자세한 내용은 [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md)을 참조하십시오.

    > [!NOTE]
    > 개발 환경이 로컬 IIS 서버를 구성할 수 있도록 하려면 관리자 권한을 가진 Visual Studio를 실행해야 합니다.

2. **Visual Studio 개발 서버**

     Visual Studio에는 ASP.NET 프로젝트의 기본 웹 서버인 기본 제공 웹 서버인 Visual Studio 개발 서버가 포함되어 있습니다. 이 웹 서버는 개발 중에 로컬 컴퓨터에서 ASP.NET 프로젝트를 실행하도록 설계되었습니다. [WCF 데이터 서비스 퀵스타트는](quickstart-wcf-data-services.md) Visual Studio 개발 서버에서 실행되는 데이터 서비스를 만드는 방법을 보여 주며, 이 에 대해 설명합니다.

     데이터 서비스를 개발하기 위해 Visual Studio 개발 서버를 사용할 때 다음 제한 사항에 유의해야 합니다.

    - 이 서버는 로컬 컴퓨터에서만 액세스할 수 있습니다.

    - 이 서버는 HTTP 메시지의 기본 포트인 특정 포트(포트 80 제외)와 `localhost` 에서 수신 대기합니다. 자세한 내용은 [Visual Studio의 ASP.NET 웹 프로젝트에 대한 웹 서버](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120))를 참조하세요.

    - 이 서버는 현재 사용자 계정의 컨텍스트에서 데이터 서비스를 실행합니다. 예를 들어 관리자 수준 사용자로 실행하는 경우 Visual Studio 개발 서버에서 실행되는 데이터 서비스에는 관리자 수준 권한이 있습니다. 따라서 데이터 서비스가 IIS 서버에 배포된 리소스 중 액세스 권한이 없는 리소스에도 액세스할 수 있습니다.

    - 이 서버에는 인증과 같은 IIS의 추가 기능이 포함되어 있지 않습니다.

    - 이 서버는 데이터 서비스에서 큰 이진 데이터에 액세스할 때 WCF 데이터 서비스 클라이언트에서 기본적으로 전송되는 청크된 HTTP 스트림을 처리할 수 없습니다. 자세한 내용은 [스트리밍 공급자](streaming-provider-wcf-data-services.md)합니다.

    - 이 서버는 이 문자가`.`주요 값의 WCF 데이터 서비스에서 지원되더라도 URL에서 기간 () 문자를 처리하는 데 문제가 있습니다.

    > [!TIP]
    > 개발 중에 Visual Studio 개발 서버를 사용하여 데이터 서비스를 테스트할 수 있지만 IIS를 실행하는 웹 서버에 배포한 후 다시 테스트해야 합니다.

3. **Microsoft Azure 개발 환경**

     Visual Studio용 Windows Azure 도구에는 Visual Studio에서 Windows Azure 서비스를 개발하기 위한 통합 도구 집합이 포함되어 있습니다. 이 도구를 사용하면 Microsoft Azure에 배포할 수 있는 데이터 서비스를 개발하고, 배포하기 전에 로컬 컴퓨터에서 데이터 서비스를 테스트할 수 있습니다. Visual Studio를 사용하여 Windows Azure 플랫폼에서 실행되는 데이터 서비스를 개발할 때 이러한 도구를 사용합니다. 도구 설치에 대한 자세한 내용은 [Visual Studio 2015용 Azure 도구를](../../../azure/sdk/vs2015-install.md)참조하십시오. Windows Azure에서 실행되는 데이터 서비스 개발에 대한 자세한 내용은 [Windows Azure에서 OData 서비스 배포](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure)게시물을 참조하십시오.

### <a name="development-tips"></a>개발 팁

데이터 서비스를 개발할 때 다음을 고려하십시오.

- 사용자를 인증하거나 특정 사용자에 대한 액세스를 제한하려는 경우 데이터 서비스의 보안 요구 사항을 결정합니다. 자세한 내용은 [Securing WCF Data Services](securing-wcf-data-services.md)을 참조하세요.

- HTTP 검사 프로그램은 요청 및 응답 메시지의 내용을 검사할 수 있도록 하여 데이터 서비스를 디버깅할 때 유용할 수 있습니다. 원시 패킷을 표시할 수 있는 네트워크 패킷 분석기를 사용하여 데이터 서비스와 주고받는 HTTP 요청 및 응답을 검사할 수 있습니다.

- 데이터 서비스를 디버깅할 때 일반 작업 보다 데이터 서비스에서 오류에 대 한 자세한 정보를 얻을 수 있습니다. <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> 에서 <xref:System.Data.Services.DataServiceConfiguration> 속성을 `true` 로 설정하고 데이터 서비스 클래스에서 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> 특성의 <xref:System.ServiceModel.Description.ServiceDebugBehavior> 속성을 `true`로 설정하여 데이터 서비스에서 추가 오류 정보를 가져올 수 있습니다. 자세한 내용은 [WCF 데이터 서비스 디버깅](https://docs.microsoft.com/archive/blogs/phaniraj/debugging-wcf-data-services)게시물을 참조하십시오. WCF에서 추적을 활성화하여 HTTP 메시징 계층에서 발생한 예외를 볼 수도 있습니다. 자세한 내용은 [Configuring Tracing](../../wcf/diagnostics/tracing/configuring-tracing.md)을 참조하세요.

- 데이터 서비스는 일반적으로 ASP.NET 응용 프로그램 프로젝트로 개발되지만 Visual Studio에서 ASP.NET 웹 사이트 프로젝트로 데이터 서비스를 만들 수도 있습니다. 두 프로젝트 유형간의 차이점에 대한 자세한 내용은 [Visual Studio의 웹 응용 프로그램 프로젝트와 웹 사이트 프로젝트를](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110))참조하십시오.

- Visual Studio에서 새 항목 **추가** 대화 상자를 사용하여 데이터 서비스를 만들면 IIS의 ASP.NET 데이터 서비스가 호스팅됩니다. ASP.NET 및 IIS는 데이터 서비스의 기본 호스트이지만 다른 호스팅 옵션이 지원됩니다. 자세한 내용은 [데이터 서비스 호스팅](hosting-the-data-service-wcf-data-services.md)합니다.

## <a name="deploy-wcf-data-services"></a>WCF 데이터 서비스 배포

WCF Data Services에서는 데이터 서비스를 호스트하는 프로세스를 유연성 있게 선택할 수 있도록 합니다. Visual Studio를 사용하여 다음 플랫폼에 데이터 서비스를 배포할 수 있습니다.

- **IIS에서 호스트되는 웹 서버**

    데이터 서비스가 ASP.NET 프로젝트로 개발되면 표준 ASP.NET 배포 프로세스를 사용하여 IIS 웹 서버에 배포할 수 있습니다.  Visual Studio는 배포하는 데이터 서비스를 호스팅하는 ASP.NET 프로젝트 의 종류에 따라 ASP.NET 대해 다음과 같은 배포 기술을 제공합니다.

  - **ASP.NET 웹 애플리케이션을 위한 배포 기술**

    - [방법: Visual Studio에서 웹 배포 패키지 만들기](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

    - [방법: Visual Studio에서 원클릭 게시를 사용하여 웹 프로젝트 배포](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

  - **ASP.NET 웹 사이트를 위한 배포 기술**

    - [방법: 복사 웹 사이트 도구를 사용하여 웹 사이트 파일 복사](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

    - [방법: 웹 사이트 게시](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

    - [연습: XCOPY를 사용하여 ASP.NET 웹 응용 프로그램 배포](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     ASP.NET 응용 프로그램에 대한 배포 옵션에 대한 자세한 내용은 [Visual Studio 및 ASP.NET 대한 웹 배포 개요를](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110))참조하십시오.

    > [!TIP]
    > 데이터 서비스를 IIS에 배포하기 전에 IIS가 실행 중인 웹 서버로의 배포를 테스트했는지 확인해야 합니다. 자세한 내용은 [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md)을 참조하십시오.

- **Windows Azure**

     Visual Studio용 Windows Azure 도구를 사용하여 데이터 서비스를 Windows Azure에 배포할 수 있습니다. [Microsoft 다운로드 센터에서](https://go.microsoft.com/fwlink/?LinkID=201848)Visual Studio용 Windows Azure 도구를 다운로드할 수 있습니다. Windows Azure에 데이터 서비스를 배포하는 것에 대한 자세한 내용은 [Windows Azure에서 OData 서비스 배포](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure)게시물을 참조하십시오.

### <a name="deployment-considerations"></a>배포 고려 사항

데이터 서비스를 배포할 때 다음을 고려하십시오.

- Entity Framework 공급자를 사용하여 SQL Server 데이터베이스에 액세스하는 데이터 서비스를 배포하는 경우 데이터 서비스 배포를 통해 데이터 구조, 데이터 또는 둘 다를 전파해야 할 수도 있습니다. Visual Studio는 대상 데이터베이스에서 이 작업을 수행하는 스크립트(.sql 파일)를 자동으로 만들 수 있으며 이러한 스크립트는 ASP.NET 응용 프로그램의 웹 배포 패키지에 포함될 수 있습니다. 자세한 내용은 [웹 응용 프로그램 프로젝트를 사용하여 데이터베이스 배포 방법을 참조하세요.](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100)) ASP.NET 웹 사이트의 경우 Visual Studio의 **데이터베이스 게시 마법사를** 사용하여 이 작업을 수행할 수 있습니다. 자세한 내용은 [SQL 데이터베이스 게시](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100))를 참조하십시오.

- WCF 데이터 서비스에는 기본 WCF 구현이 포함되어 있으므로 Windows Server AppFabric을 사용하여 Windows 서버에서 실행되는 IIS에 배포된 데이터 서비스를 모니터링할 수 있습니다. Windows Server AppFabric을 사용하여 데이터 서비스를 모니터링하는 데 대한 자세한 내용은 [Windows Server AppFabric을 사용하여 WCF 데이터 서비스 추적](https://docs.microsoft.com/archive/blogs/rjacobs/tracking-wcf-data-services-with-windows-server-appfabric)게시물을 참조하십시오.

## <a name="see-also"></a>참고 항목

- [데이터 서비스 호스팅](hosting-the-data-service-wcf-data-services.md)
- [WCF Data Services에 보안 설정](securing-wcf-data-services.md)
- [WCF Data Services 정의](defining-wcf-data-services.md)
