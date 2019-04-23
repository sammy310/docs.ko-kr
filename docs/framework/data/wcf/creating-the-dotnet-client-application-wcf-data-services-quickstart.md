---
title: .NET Framework 클라이언트 응용 프로그램 만들기(WCF Data Services 빠른 시작)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: dfc08d4623f124a41412907f5a118e8d9ee7833d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517774"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>.NET Framework 클라이언트 응용 프로그램 만들기(WCF Data Services 빠른 시작)

WCF Data Services 빠른 시작의 최종 작업입니다. 이 태스크에서는 솔루션에 콘솔 응용 프로그램을 추가에 대 한 참조가 추가 됩니다는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 이 새 클라이언트 응용 프로그램으로 피드 및 생성 된 클라이언트 데이터 서비스 클래스와 클라이언트 라이브러리를 사용 하 여 클라이언트 응용 프로그램에서 피드 OData 액세스 .

> [!NOTE]
> 데이터 피드에 액세스하기 위해 .NET Framework 기반 클라이언트 응용 프로그램이 필요하지는 않습니다. 데이터 서비스 OData 피드를 사용 하는 모든 응용 프로그램 구성 요소에서 액세스할 수 있습니다. 자세한 내용은 [클라이언트 응용 프로그램에서 데이터 서비스를 사용 하 여](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)입니다.

## <a name="to-create-the-client-application-by-using-visual-studio"></a>Visual Studio를 사용하여 클라이언트 응용 프로그램을 만들려면

1. **솔루션 탐색기**솔루션을 마우스 오른쪽 단추로 클릭, 클릭 **추가**를 클릭 하 고 **새 프로젝트**합니다.

2. 왼쪽된 창에서 선택 **설치 됨** > [**시각적 C#**  또는 **Visual Basic**] > **Windows Desktop**를 선택한 다음 합니다  **WPF 앱** 템플릿.

3. 입력 `NorthwindClient` 클릭 한 다음 확인 하 고 프로젝트 이름에 대 한 **확인**합니다.

4. MainWindow.xaml 파일을 열고 XAML 코드를 다음 코드로 바꿉니다.

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a>프로젝트에 데이터 서비스 참조를 추가하려면

1. **솔루션 탐색기**NorthwindClient 프로젝트를 마우스 오른쪽 단추로 클릭, 클릭 **추가** > **서비스 참조**를 클릭 하 고 **검색** .

     첫 번째 작업에서 만든 Northwind 데이터 서비스가 표시됩니다.

2. 에 **Namespace** 텍스트 상자에서 `Northwind`를 클릭 하 고 **확인**합니다.

     데이터 서비스 리소스에 개체로 액세스하고 상호 작용하는 데 사용되는 데이터 클래스가 포함된 새 코드 파일이 프로젝트에 추가됩니다. 데이터 클래스는 `NorthwindClient.Northwind` 네임스페이스에 만들어집니다.

## <a name="to-access-data-service-data-in-the-wpf-application"></a>WPF 응용 프로그램에서 데이터 서비스 데이터에 액세스하려면

1. **솔루션 탐색기** 아래에서 **NorthwindClient**프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **참조 추가**합니다.

2. 에 **참조 추가** 대화 상자에서 클릭 합니다 **.NET** 탭 하 고 System.Data.Services.Client.dll 어셈블리를 선택한 다음 클릭 **확인**합니다.

3. **솔루션 탐색기** 아래에서 **NorthwindClient**을 MainWindow.xaml 파일의 코드 페이지를 열고 다음을 추가 합니다 `using` 문 (`Imports` Visual basic에서).

     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

3. 해당 데이터 서비스를 쿼리하고 결과를 <xref:System.Data.Services.Client.DataServiceCollection%601>에 바인딩하는 다음 코드를 `MainWindow` 클래스에 삽입합니다.

    > [!NOTE]
    > Northwind 데이터 서비스 인스턴스를 호스트하는 서버 및 포트로 호스트 이름 `localhost:12345`를 바꾸어야 합니다.

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

4. 변경 내용을 저장하는 다음 코드를 `MainWindow` 클래스에 삽입합니다.

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a>NorthwindClient 응용 프로그램을 빌드 및 실행하려면

1. **솔루션 탐색기**NorthwindClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트로 설정**합니다.

2. 키를 눌러 **F5** 응용 프로그램을 시작 합니다.

     솔루션이 빌드되고 클라이언트 응용 프로그램이 시작됩니다. 서비스에서 데이터가 요청되고 콘솔에 표시됩니다.

3. 값을 편집 합니다 **수량** 클릭 한 다음 확인 하 고 데이터 표에서 열의 **저장**합니다.

     변경 내용이 데이터 서비스에 저장됩니다.

    > [!NOTE]
    > 이 버전의 NorthwindClient 응용 프로그램은 엔터티의 추가와 삭제를 지원하지 않습니다.

## <a name="next-steps"></a>다음 단계

샘플 Northwind OData 피드에서 액세스 하는 클라이언트 응용 프로그램을 만들었습니다. WCF Data Services 퀵 스타트도 완료 했습니다.

OData에 액세스 하는 방법에 대 한 자세한 내용은에서 피드를 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램을 참조 하세요 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)합니다.

## <a name="see-also"></a>참고자료

- [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [리소스](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
