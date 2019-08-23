---
title: '방법: 클라이언트 데이터 서비스 클래스를 수동으로 생성 (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 2a827e4909b18d9cca74fc20a2d83d2730ea0cd9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952293"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="ee9dd-102">방법: 클라이언트 데이터 서비스 클래스를 수동으로 생성 (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ee9dd-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="ee9dd-103">WCF Data Services는 visual Studio와 통합 되어 **서비스 참조 추가** 대화 상자를 사용 하 여 visual studio 프로젝트에서 데이터 서비스에 대 한 참조를 추가할 때 자동으로 클라이언트 데이터 서비스 클래스를 생성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="ee9dd-104">자세한 내용은 [방법: 데이터 서비스 참조](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="ee9dd-105">코드 생성 도구 `DataSvcUtil.exe`를 사용하여 동일한 클라이언트 데이터 서비스 클래스를 수동으로 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="ee9dd-106">WCF Data Services에 포함 된이 도구는 데이터 서비스 정의에서 .NET Framework 클래스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="ee9dd-107">이 도구를 사용하여 개념적 모델 파일(.csdl) 및 Visual Studio 프로젝트의 Entity Framework 모델을 나타내는 .edmx 파일에서 데이터 서비스 클래스를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="ee9dd-108">이 항목의 예제에서는 Northwind 샘플 데이터 서비스를 기반으로 하여 클라이언트 데이터 서비스 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="ee9dd-109">이 서비스는 [WCF Data Services 빠른](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="ee9dd-110">이 항목의 일부 예제에는 Northwind 모델에 대한 개념적 모델 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="ee9dd-111">자세한 내용은 [방법: Edmgen.exe를 사용 하 여 모델 및 매핑 파일](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="ee9dd-112">이 항목의 일부 예제에는 Northwind 모델에 대한 .edmx 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="ee9dd-113">자세한 내용은 [.Edmx 파일 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-113">For more information, see [.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="ee9dd-114">데이터 바인딩을 지원하는 C# 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ee9dd-114">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="ee9dd-115">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="ee9dd-116">`/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="ee9dd-117">데이터 바인딩을 지원하는 Visual Basic 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ee9dd-117">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="ee9dd-118">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="ee9dd-119">`/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="ee9dd-120">서비스 URI를 기반으로 하여 C# 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ee9dd-120">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="ee9dd-121">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="ee9dd-122">`/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="ee9dd-123">서비스 URI를 기반으로 하여 Visual Basic 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ee9dd-123">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="ee9dd-124">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="ee9dd-125">`/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="ee9dd-126">개념적 모델 파일(CSDL)을 기반으로 하여 C# 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ee9dd-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="ee9dd-127">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="ee9dd-128">개념적 모델 파일(CSDL)을 기반으로 하여 Visual Basic 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ee9dd-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="ee9dd-129">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="ee9dd-130">.edmx 파일을 기반으로 하여 C# 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ee9dd-130">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="ee9dd-131">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="ee9dd-132">.edmx 파일을 기반으로 하여 Visual Basic 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ee9dd-132">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="ee9dd-133">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9dd-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="ee9dd-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee9dd-134">See also</span></span>

- [<span data-ttu-id="ee9dd-135">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="ee9dd-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="ee9dd-136">방법: 데이터 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="ee9dd-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="ee9dd-137">WCF Data Services 클라이언트 유틸리티(DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="ee9dd-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
