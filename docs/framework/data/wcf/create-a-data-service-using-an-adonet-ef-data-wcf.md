---
title: '방법: ADO.NET Entity Framework 데이터 원본을 (WCF Data Services)를 사용 하 여 데이터 서비스 만들기'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 7dd93e5aa44effcf9fc41598e41f6f612a209c86
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307140"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>방법: ADO.NET Entity Framework 데이터 원본을 (WCF Data Services)를 사용 하 여 데이터 서비스 만들기

WCF Data Services에서는 엔터티 데이터를 데이터 서비스로 노출 합니다. 이 엔터티 데이터를 ADO.NET으로 제공 되는[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 경우 데이터 원본이 관계형 데이터베이스입니다. 이 항목에서는 만드는 방법을 보여 줍니다.는 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-기존 데이터베이스를 기반으로 하며이 데이터 모델을 사용 하 여 새 데이터 서비스를 만들려면 Visual Studio 웹 응용 프로그램에서 데이터 모델을 기반으로 합니다.

합니다 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 생성할 수 있는 명령줄 도구도 제공는 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Visual Studio 프로젝트 외부의 모델입니다. 자세한 내용은 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 생성](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>기존 웹 애플리케이션에 기존 데이터베이스를 기반으로 하는 Entity Framework 모델을 추가하려면

1. 에 **프로젝트** 메뉴에서 클릭 **추가** > **새 항목**합니다.

2. 에 **템플릿을** 창 클릭 합니다 **데이터** 범주를 선택한 후 **ADO.NET 엔터티 데이터 모델**합니다.

3. 모델 이름을 입력 한 다음 클릭 **추가**합니다.

     엔터티 데이터 모델 마법사 시작 페이지가 표시됩니다.

4. 에 **모델 콘텐츠 선택** 대화 상자에서 **데이터베이스에서 생성**합니다. **다음**을 클릭합니다.

5. 클릭 합니다 **새 연결** 단추입니다.

6. 에 **연결 속성** 대화 상자에서 서버 이름을 입력, 인증 방법을 선택, 데이터베이스 이름으로 입력 및 클릭 **확인**합니다.

     합니다 **데이터 연결 선택** 대화 상자가 데이터베이스 연결 설정을 사용 하 여 업데이트 됩니다.

7. 있는지 확인 합니다 **으로 App.Config의 entity 연결 설정 저장:** 확인란이 선택 되어 있습니다. **다음**을 클릭합니다.

8. 에 **데이터베이스 개체 선택** 대화 상자에서 선택한 모든 데이터베이스의 데이터 서비스에 노출 하려는 개체입니다.

    > [!NOTE]
    > 데이터 모델에 포함된 개체는 데이터 서비스에 의해 자동으로 노출되지 않습니다. 서비스 자체에서 해당 개체를 명시적으로 노출해야 합니다. 자세한 내용은 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)합니다.

9. 클릭 **완료** 마법사를 완료 합니다.

     특정 데이터베이스를 기반으로 하는 기본 데이터 모델이 만들어집니다. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]에서는 데이터 모델을 사용자 지정할 수 있습니다. 자세한 내용은 [엔터티 데이터 모델 도구 작업](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100))합니다.

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a>새 데이터 모델을 사용하여 데이터 서비스를 만들려면

1. Visual Studio에서 데이터 모델을 나타내는 .edmx 파일을 엽니다.

2. 에 **Model 브라우저**모델을 마우스 오른쪽 단추로 클릭, 클릭 **속성**, 다음 엔터티 컨테이너의 이름을 기록해 둡니다.

3. **솔루션 탐색기**ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **추가** > **새 항목**합니다.

4. 에 **새 항목 추가** 대화 상자에서를 **WCF 데이터 서비스** 에서 서식 파일을 **웹** 범주.

   ![Visual Studio 2015에서 WCF 데이터 서비스 항목 템플릿](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > 합니다 **WCF 데이터 서비스** 서식 파일은 Visual Studio 2015 하지만 되지에 Visual Studio 2017에서 사용할 수 있습니다.

5. 서비스에 대 한 이름을 입력 한 다음 클릭 **확인**합니다.

     Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다. 기본적으로 코드 편집기 창이 열립니다.

6. 데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 <xref:System.Data.Objects.ObjectContext> 클래스에서 상속되고 2단계에서 적어 둔 데이터 모델의 엔터티 컨테이너인 형식으로 바꿉니다.

7. 데이터 서비스 코드에서 권한 있는 클라이언트가 데이터 서비스에서 노출하는 엔터티 집합에 액세스할 수 있도록 합니다. 자세한 내용은 [데이터 서비스 만들기](../../../../docs/framework/data/wcf/creating-the-data-service.md)합니다.

8. 웹 브라우저를 사용 하 여 Northwind.svc 데이터 서비스를 테스트 하려면 항목의 지침을 따릅니다 [웹 브라우저에서 서비스 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)합니다.

## <a name="see-also"></a>참고자료

- [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Data Services 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [방법: LINQ to SQL 데이터 원본을 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
