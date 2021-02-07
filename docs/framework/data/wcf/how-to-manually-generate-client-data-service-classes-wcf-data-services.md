---
description: '자세한 정보: 방법: 클라이언트 데이터 서비스 클래스 수동 생성 (WCF Data Services)'
title: '방법: 수동으로 클라이언트 데이터 서비스 클래스 생성(WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 6fe878e1177055540a29fb84252eddaa4d97e536
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765206"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="c8733-103">방법: 수동으로 클라이언트 데이터 서비스 클래스 생성(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="c8733-103">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="c8733-104">WCF Data Services는 visual Studio와 통합 되어 **서비스 참조 추가** 대화 상자를 사용 하 여 visual studio 프로젝트에서 데이터 서비스에 대 한 참조를 추가할 때 자동으로 클라이언트 데이터 서비스 클래스를 생성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-104">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="c8733-105">자세한 내용은 [방법: 데이터 서비스 참조 추가](how-to-add-a-data-service-reference-wcf-data-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8733-105">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="c8733-106">코드 생성 도구 `DataSvcUtil.exe`를 사용하여 동일한 클라이언트 데이터 서비스 클래스를 수동으로 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-106">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="c8733-107">WCF Data Services에 포함 된이 도구는 데이터 서비스 정의에서 .NET Framework 클래스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-107">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="c8733-108">이 도구를 사용하여 개념적 모델 파일(.csdl) 및 Visual Studio 프로젝트의 Entity Framework 모델을 나타내는 .edmx 파일에서 데이터 서비스 클래스를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-108">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="c8733-109">이 항목의 예제에서는 Northwind 샘플 데이터 서비스를 기반으로 하여 클라이언트 데이터 서비스 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-109">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="c8733-110">이 서비스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-110">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="c8733-111">이 항목의 일부 예제에는 Northwind 모델에 대한 개념적 모델 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-111">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="c8733-112">자세한 내용은 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 생성](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8733-112">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="c8733-113">이 항목의 일부 예제에는 Northwind 모델에 대한 .edmx 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-113">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="c8733-114">자세한 내용은 [.Edmx 파일 개요](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8733-114">For more information, see [.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="c8733-115">데이터 바인딩을 지원하는 C# 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="c8733-115">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="c8733-116">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-116">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="c8733-117">`/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-117">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="c8733-118">데이터 바인딩을 지원하는 Visual Basic 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="c8733-118">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="c8733-119">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-119">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="c8733-120">`/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-120">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="c8733-121">서비스 URI를 기반으로 하여 C# 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="c8733-121">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="c8733-122">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-122">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="c8733-123">`/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-123">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="c8733-124">서비스 URI를 기반으로 하여 Visual Basic 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="c8733-124">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="c8733-125">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-125">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="c8733-126">`/uri:` 매개 변수에 제공된 값을 Northwind 샘플 데이터 서비스 인스턴스의 URI로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-126">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="c8733-127">개념적 모델 파일(CSDL)을 기반으로 하여 C# 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="c8733-127">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="c8733-128">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-128">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="c8733-129">개념적 모델 파일(CSDL)을 기반으로 하여 Visual Basic 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="c8733-129">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="c8733-130">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-130">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="c8733-131">.edmx 파일을 기반으로 하여 C# 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="c8733-131">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="c8733-132">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-132">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="c8733-133">.edmx 파일을 기반으로 하여 Visual Basic 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="c8733-133">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="c8733-134">명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8733-134">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="c8733-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8733-135">See also</span></span>

- [<span data-ttu-id="c8733-136">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="c8733-136">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="c8733-137">방법: 데이터 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="c8733-137">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="c8733-138">WCF Data Services 클라이언트 유틸리티(DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="c8733-138">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](wcf-data-service-client-utility-datasvcutil-exe.md)
