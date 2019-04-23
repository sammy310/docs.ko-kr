---
title: Visual Studio에서 WCF 데이터 서비스 만들기
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: e8d82ff8958af12842366911b6633ea6b2e0efbb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517228"
---
# <a name="create-the-data-service"></a>데이터 서비스 만들기

이 항목에서는 WCF Data Services를 사용 하 여 노출 하는 샘플 데이터 서비스를 만들면는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Northwind 샘플 데이터베이스를 기반으로 하는 피드 합니다. 작업에 필요한 기본 단계는 다음과 같습니다.

1. ASP.NET 웹 응용 프로그램을 만듭니다.

2. 엔터티 데이터 모델 도구를 사용하여 데이터 모델을 정의합니다.

3. 웹 응용 프로그램에 데이터 서비스를 추가합니다.

4. 데이터 서비스에 액세스할 수 있도록 설정합니다.

## <a name="create-the-aspnet-web-app"></a>ASP.NET 웹 앱 만들기

1. Visual Studio에서에 **파일** 메뉴에서 **새로 만들기** > **프로젝트**합니다.

1. 에 **새 프로젝트** Visual Basic 또는 Visual C# 선택 대화 상자를 **웹** 범주를 선택한 후 **ASP.NET 웹 응용 프로그램**합니다.

1. 입력 `NorthwindService` 한 다음 선택한 프로젝트의 이름으로 **확인**합니다.

1. 에 **새 ASP.NET 웹 응용 프로그램** 대화 상자에서 **빈** 선택한 후 **확인**합니다.

1. (선택 사항) 웹 응용 프로그램의 특정 포트 번호를 지정합니다. 참고: 포트 번호 `12345` 이 일련의 빠른 시작 항목에 사용 됩니다.

    1. **솔루션 탐색기**방금 만든 ASP.NET 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택한 **속성**합니다.

    2. 선택는 **웹** 탭을 선택한 값을 설정 합니다 **특정 포트** 텍스트 상자 `12345`합니다.

## <a name="define-the-data-model"></a>데이터 모델 정의

1. **솔루션 탐색기**ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **추가** > **새 항목**합니다.

2. 에 **새 항목 추가** 대화 상자를 선택 합니다 **데이터** 범주를 선택한 후 **ADO.NET 엔터티 데이터 모델**합니다.

3. 데이터 모델의 이름에 대 한 입력 `Northwind.edmx`합니다.

4. 에 **엔터티 데이터 모델 마법사**를 선택 **데이터베이스의 EF 디자이너**를 클릭 하 고 **다음**합니다.

5. 다음 단계 중 하나를 수행 하 여 데이터 모델 데이터베이스에 연결 하 고 클릭 **다음**:

    -   이미 구성 된 데이터베이스 연결 목록에 없으면 클릭 **새 연결** 새 연결을 만듭니다. 자세한 내용은 [방법: SQL Server 데이터베이스에 연결을 만들](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))합니다. 이 SQL Server 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.

         \- 또는 -

    -   Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.

6. 마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.

7. **마침** 을 클릭하여 마법사를 닫습니다.

## <a name="create-the-wcf-data-service"></a>WCF 데이터 서비스 만들기

1. **솔루션 탐색기**ASP.NET 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택한 **추가** > **새 항목**합니다.

2. 에 **새 항목 추가** 대화 상자에서를 **WCF Data Service** 항목 템플릿에서 **웹** 범주.

   ![Visual Studio 2015에서 WCF 데이터 서비스 항목 템플릿](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > 합니다 **WCF 데이터 서비스** 서식 파일은 Visual Studio 2015 하지만 되지에 Visual Studio 2017에서 사용할 수 있습니다.

3. 서비스의 이름에 대 한 입력 `Northwind`합니다.

     Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다. 기본적으로 코드 편집기 창이 열립니다. **솔루션 탐색기**, 서비스에 확장을 사용 하 여 Northwind 이름의 *. svc.cs* 하거나 *. svc.vb*.

4. 데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindEntities`)으로 바꿉니다. 클래스 정의는 다음과 같이 나타납니다.

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>데이터 서비스 리소스에 대 한 액세스를 사용 하도록 설정

1. 데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     이렇게 하면 권한 있는 클라이언트가 지정된 엔터티 집합의 리소스에 대한 읽기 및 쓰기 액세스 권한을 가질 수 있습니다.

    > [!NOTE]
    > ASP.NET 응용 프로그램에 액세스할 수 있는 클라이언트는 데이터 서비스에 의해 노출되는 리소스에도 액세스할 수 있습니다. 리소스에 무단으로 액세스할 수 없도록 하려면 프로덕션 데이터 서비스에서 응용 프로그램 자체에도 보안을 설정해야 합니다. 자세한 내용은 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계

Northwind 샘플 데이터베이스를 기반으로 하는 OData 피드를 노출 하는 새 데이터 서비스를 성공적으로 만들었습니다 ASP.NET 웹 응용 프로그램에 대 한 사용 권한이 있는 클라이언트의 피드에 대 한 액세스를 사용 하는 합니다. 다음으로 Visual Studio에서 데이터 서비스를 시작 하 고 OData 피드에 웹 브라우저를 통해 HTTP GET 요청을 제출 하 여 액세스 됩니다.

> [!div class="nextstepaction"]
> [웹 브라우저에서 서비스에 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>참고자료

- [ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))