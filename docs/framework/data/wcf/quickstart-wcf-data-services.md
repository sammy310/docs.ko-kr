---
title: 빠른 시작(WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121219"
---
# <a name="quickstart-wcf-data-services"></a>빠른 시작(WCF Data Services)

이 빠른 시작을 통해 시작 항목의 항목을 지원하는 일련의 작업을 통해 WCF 데이터 서비스 및 [Getting Started](getting-started-with-wcf-data-services.md)OData(개방형 데이터 프로토콜)에 익숙해질 수 있습니다.

## <a name="what-youll-learn"></a>학습할 내용

이 빠른 시작의 첫 번째 작업은 Northwind 샘플 데이터베이스에서 OData 피드를 노출하는 데이터 서비스를 만드는 방법을 보여 주며 있습니다. 이후 항목에서는 웹 브라우저를 사용하여 OData 피드에 액세스하고 클라이언트 라이브러리를 사용하여 OData 피드를 사용하는 WPF(Windows 프레젠테이션 기반) 클라이언트 응용 프로그램을 만듭니다.

## <a name="prerequisites"></a>사전 요구 사항

이 빠른 시작을 완료하려면 다음 구성 요소를 설치합니다.

- Visual Studio

- SQL 서버의 인스턴스입니다. 여기에는 Visual Studio 2015의 기본 설치에 포함되는 SQL Server Express 또는 Visual Studio 2017 이상의 **데이터 저장소 및 처리** 워크로드의 일부로 포함됩니다.

- Northwind 샘플 데이터베이스 데이터베이스를 설치하려면 [노스윈드에서](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)Transact-SQL 스크립트를 실행하고 Microsoft SQL Server에 대한 펍 샘플 데이터베이스를 실행합니다.

## <a name="wcf-data-services-quickstart-tasks"></a>WCF 데이터 서비스 빠른 시작 작업

 [데이터 서비스 만들기](creating-the-data-service.md)

 ASP.NET 애플리케이션과 데이터 모델을 정의하고, 데이터 서비스를 만들고, 리소스에 액세스할 수 있도록 합니다.

 [웹 브라우저에서 서비스에 액세스](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Visual Studio에서 서비스를 시작하고 웹 브라우저를 통해 HTTP GET 요청을 노출된 피드로 전송하여 서비스에 액세스합니다.

 [.NET 프레임워크 클라이언트 응용 프로그램 만들기](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 WPF 앱을 만들어 OData 피드를 사용하고, 데이터를 Windows 컨트롤에 바인딩하고, 바인딩된 컨트롤의 데이터를 변경한 다음 변경 내용을 데이터 서비스로 다시 보냅니다.

> [!NOTE]
> 완료된 버전의 퀵스타트에서 프로젝트 파일을 [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))에서 다운로드할 수 있습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [빠른 시작 시작](creating-the-data-service.md)

## <a name="see-also"></a>참조

- [ADO.NET Entity Framework](../adonet/ef/index.md)
