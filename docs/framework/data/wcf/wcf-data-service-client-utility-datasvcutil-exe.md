---
title: WCF Data Services 클라이언트 유틸리티(DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: bf812f45e4a4090becd8dfafe035d39d1d851860
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583651"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a><span data-ttu-id="963d7-102">WCF Data Services 클라이언트 유틸리티(DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="963d7-102">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>

<span data-ttu-id="963d7-103">DataSvcUtil.exe는를 사용 하는 WCF Data Services에서 제공 하는 명령줄 도구는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드 및.NET Framework 클라이언트 응용 프로그램에서 데이터 서비스에 액세스 하는 데 필요한 클라이언트 데이터 서비스 클래스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-103">DataSvcUtil.exe is a command-line tool provided by WCF Data Services that consumes an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed and generates the client data service classes that are needed to access a data service from a .NET Framework client application.</span></span> <span data-ttu-id="963d7-104">이 유틸리티는 다음 메타데이터 소스를 사용하여 데이터 클래스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-104">This utility can generate data classes by using the following metadata sources:</span></span>

- <span data-ttu-id="963d7-105">데이터 서비스의 루트 URI</span><span class="sxs-lookup"><span data-stu-id="963d7-105">The root URI of a data service.</span></span> <span data-ttu-id="963d7-106">이 유틸리티는 데이터 서비스에서 노출하는 데이터 모델을 설명하는 서비스 메타데이터 문서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-106">The utility requests the service metadata document, which describes the data model exposed by the data service.</span></span> <span data-ttu-id="963d7-107">자세한 내용은 참조 하세요. [OData: 서비스 메타 데이터 문서](https://go.microsoft.com/fwlink/?LinkId=186070)합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-107">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span>

- <span data-ttu-id="963d7-108">에 정의 된 개념 스키마 정의 언어 (CSDL)을 사용 하 여 정의 된 데이터 모델 파일 (.csdl)는 [ \[MC-CSDL\]: Conceptual Schema Definition File Format](https://go.microsoft.com/fwlink/?LinkID=159072) 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-108">A data model file (.csdl) defined by using the conceptual schema definition language (CSDL), as defined in the [\[MC-CSDL\]: Conceptual Schema Definition File Format](https://go.microsoft.com/fwlink/?LinkID=159072) specification.</span></span>

- <span data-ttu-id="963d7-109">Entity Framework와 함께 제공되는 엔터티 데이터 모델 도구를 사용하여 만든 .edmx 파일.</span><span class="sxs-lookup"><span data-stu-id="963d7-109">An .edmx file created by using the Entity Data Model tools that are provided with the Entity Framework.</span></span> <span data-ttu-id="963d7-110">자세한 내용은 참조는 [ \[MC-EDMX\]: Data Services 패키징 형식의 엔터티 데이터 모델](https://go.microsoft.com/fwlink/?LinkID=178833) 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-110">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification.</span></span>

<span data-ttu-id="963d7-111">자세한 내용은 [방법: 수동으로 클라이언트 데이터 서비스 클래스 생성](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-111">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>

<span data-ttu-id="963d7-112">DataSvcUtil.exe 도구는.NET Framework 디렉터리에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-112">The DataSvcUtil.exe tool is installed in the .NET Framework directory.</span></span> <span data-ttu-id="963d7-113">대부분의 경우에서이에 위치한 *C:\Windows\Microsoft.NET\Framework\v4.0*합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-113">In many cases, this is located in *C:\Windows\Microsoft.NET\Framework\v4.0*.</span></span> <span data-ttu-id="963d7-114">64 비트 시스템의 경우이에 위치한 *C:\Windows\Microsoft.NET\Framework64\v4.0*합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-114">For 64-bit systems, this is located in *C:\Windows\Microsoft.NET\Framework64\v4.0*.</span></span> <span data-ttu-id="963d7-115">작업을 Visual Studio 용 개발자 명령 프롬프트에서 DataSvcUtil.exe 도구도 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-115">You can also access the DataSvcUtil.exe tool from Developer Command Prompt for Visual Studio.</span></span>

## <a name="syntax"></a><span data-ttu-id="963d7-116">구문</span><span class="sxs-lookup"><span data-stu-id="963d7-116">Syntax</span></span>

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a><span data-ttu-id="963d7-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="963d7-117">Parameters</span></span>

|<span data-ttu-id="963d7-118">옵션</span><span class="sxs-lookup"><span data-stu-id="963d7-118">Option</span></span>|<span data-ttu-id="963d7-119">설명</span><span class="sxs-lookup"><span data-stu-id="963d7-119">Description</span></span>|
|------------|-----------------|
|`/dataservicecollection`|<span data-ttu-id="963d7-120">개체를 컨트롤에 바인딩하는 데 필요한 코드도 생성되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-120">Specifies that the code required to bind objects to controls is also generated.</span></span>|
|`/help`<br /><br /> <span data-ttu-id="963d7-121">또는</span><span class="sxs-lookup"><span data-stu-id="963d7-121">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="963d7-122">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-122">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="963d7-123">`/in:` *\<file>*</span><span class="sxs-lookup"><span data-stu-id="963d7-123">`/in:` *\<file>*</span></span>|<span data-ttu-id="963d7-124">.csdl 또는 .edmx 파일이나 파일이 있는 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-124">Specifies the .csdl or .edmx file or a directory where the file is located.</span></span>|
|<span data-ttu-id="963d7-125">`/language:`[VB&#124;CSharp]</span><span class="sxs-lookup"><span data-stu-id="963d7-125">`/language:`[VB&#124;CSharp]</span></span>|<span data-ttu-id="963d7-126">생성되는 소스 코드 파일의 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-126">Specifies the language for the generated source code files.</span></span> <span data-ttu-id="963d7-127">기본 언어는 C#입니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-127">The language defaults to C#.</span></span>|
|`/nologo`|<span data-ttu-id="963d7-128">저작권 메시지가 표시되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-128">Suppresses the copyright message from displaying.</span></span>|
|<span data-ttu-id="963d7-129">`/out:` *\<file>*</span><span class="sxs-lookup"><span data-stu-id="963d7-129">`/out:` *\<file>*</span></span>|<span data-ttu-id="963d7-130">생성된 클라이언트 데이터 서비스 클래스가 포함되는 소스 코드 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-130">Specifies the name of the source code file that contains the generated client data service classes.</span></span>|
|<span data-ttu-id="963d7-131">`/uri:` *\<string>*</span><span class="sxs-lookup"><span data-stu-id="963d7-131">`/uri:` *\<string>*</span></span>|<span data-ttu-id="963d7-132">OData 피드의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-132">The URI of the OData feed.</span></span>|
|<span data-ttu-id="963d7-133">`/version:`[1.0&#124;2.0]</span><span class="sxs-lookup"><span data-stu-id="963d7-133">`/version:`[1.0&#124;2.0]</span></span>|<span data-ttu-id="963d7-134">OData의 허용 된 가장 높은 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-134">Specifies the highest accepted version of OData.</span></span> <span data-ttu-id="963d7-135">버전에 따라 결정 됩니다는 `DataServiceVersion` 반환 되는 데이터 서비스 메타 데이터에 있는 DataService 요소의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-135">The version is determined based on the `DataServiceVersion` attribute of the DataService element in the returned data service metadata.</span></span> <span data-ttu-id="963d7-136">자세한 내용은 [데이터 서비스 버전 관리](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-136">For more information, see [Data Service Versioning](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).</span></span> <span data-ttu-id="963d7-137">지정 하는 경우는 `/dataservicecollection` 매개 변수를 지정 해야 `/version:2.0` 데이터 바인딩을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="963d7-137">When you specify the `/dataservicecollection` parameter, you must also specify `/version:2.0` to enable data binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="963d7-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="963d7-138">See also</span></span>

- [<span data-ttu-id="963d7-139">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="963d7-139">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="963d7-140">방법: 데이터 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="963d7-140">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
