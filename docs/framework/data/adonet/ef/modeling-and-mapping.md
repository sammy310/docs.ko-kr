---
title: 모델링 및 매핑
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 33064d35b7ac4c469df3ca6f0111cc84ef10eb08
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248493"
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="9f29f-102">모델링 및 매핑</span><span class="sxs-lookup"><span data-stu-id="9f29f-102">Modeling and Mapping</span></span>
<span data-ttu-id="9f29f-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서는 애플리케이션에 가장 적합한 방식으로 개념적 모델, 스토리지 모델 및 두 모델 간의 매핑을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f29f-103">In the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="9f29f-104">Visual Studio의 엔터티 데이터 모델 도구를 사용 하 여를 만들 수 있습니다. 데이터베이스나 모델이 변경 될 때 데이터베이스 또는 그래픽 모델의 [edmx 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) 을 업데이트 한 다음 해당 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f29f-104">The Entity Data Model Tools in Visual Studio allow you to create an .[edmx file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="9f29f-105">Entity Framework 4.1부터는 Code First 개발을 통해 모델을 프로그램 방식으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f29f-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="9f29f-106">Code First 개발에는 두 가지 다른 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f29f-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="9f29f-107">두 경우 모두 개발자는 .NET Framewor 클래스 정의를 코딩하여 모델을 정의한 후 데이터 주석 또는 fluent API를 사용하여 추가 매핑 또는 구성을 선택적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f29f-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="9f29f-108">자세한 내용은 [개념적 모델 만들기 및 매핑](https://go.microsoft.com/fwlink/?LinkId=235016)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f29f-108">For more information, see [Creating and Mapping a Conceptual Model](https://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="9f29f-109">.NET Framework에 포함 된 EDM 생성기를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f29f-109">You can also use the EDM Generator, which is included with the .NET Framework.</span></span> <span data-ttu-id="9f29f-110">EdmGen.exe 생성기는 기존 데이터 소스에서 .csdl, .ssdl 및 .msl 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f29f-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="9f29f-111">또한 모델 및 매핑 콘텐츠를 수동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f29f-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="9f29f-112">자세한 내용은 [EDM 생성기 (edmgen.exe)](edm-generator-edmgen-exe.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f29f-112">For more information, see [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md).</span></span>
