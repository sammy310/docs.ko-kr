---
title: '방법: 수동으로 클라이언트 데이터 서비스 클래스 (WCF Data Services)를 생성'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 86cf9a622f244fd6ea13113310eb05f65da1463f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645608"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>방법: 수동으로 클라이언트 데이터 서비스 클래스 (WCF Data Services)를 생성
WCF Data Services를 사용 하는 경우 클라이언트 데이터 서비스 클래스를 자동으로 생성할 수 있도록 Visual Studio와 통합 된 **서비스 참조 추가** Visual Studio 프로젝트에서 데이터 서비스에 대 한 참조를 추가 하려면 대화 상자. 자세한 내용은 [방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)합니다. 코드 생성 도구 `DataSvcUtil.exe`를 사용하여 동일한 클라이언트 데이터 서비스 클래스를 수동으로 생성할 수도 있습니다. WCF Data Services에 포함 된이 도구는 데이터 서비스 정의에서.NET Framework 클래스를 생성 합니다. 이 도구를 사용하여 개념적 모델 파일(.csdl) 및 Visual Studio 프로젝트의 Entity Framework 모델을 나타내는 .edmx 파일에서 데이터 서비스 클래스를 생성할 수도 있습니다.

 이 항목의 예제에서는 Northwind 샘플 데이터 서비스를 기반으로 하여 클라이언트 데이터 서비스 클래스를 만듭니다. 이 서비스를 완료할 때 만든 합니다 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다. 이 항목의 일부 예제에는 Northwind 모델에 대한 개념적 모델 파일이 필요합니다. 자세한 내용은 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 생성](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다. 이 항목의 일부 예제에는 Northwind 모델에 대한 .edmx 파일이 필요합니다. 자세한 내용은 [.edmx 파일 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))합니다.

### <a name="to-generate-c-classes-that-support-data-binding"></a>데이터 바인딩을 지원하는 C# 클래스를 생성하려면

- 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  `/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>데이터 바인딩을 지원하는 Visual Basic 클래스를 생성하려면

- 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  `/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.

### <a name="to-generate-c-classes-based-on-the-service-uri"></a>서비스 URI를 기반으로 하여 C# 클래스를 생성하려면

- 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  `/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>서비스 URI를 기반으로 하여 Visual Basic 클래스를 생성하려면

- 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  `/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>개념적 모델 파일(CSDL)을 기반으로 하여 C# 클래스를 생성하려면

- 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>개념적 모델 파일(CSDL)을 기반으로 하여 Visual Basic 클래스를 생성하려면

- 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>.edmx 파일을 기반으로 하여 C# 클래스를 생성하려면

- 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>.edmx 파일을 기반으로 하여 Visual Basic 클래스를 생성하려면

- 명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a>참고자료

- [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [WCF Data Services 클라이언트 유틸리티(DataSvcUtil.exe)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)