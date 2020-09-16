---
title: 모델링 및 매핑
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 1488b2f6bd9dde5538144f886f1fb5e01ac0de3f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554933"
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="a30b1-102">모델링 및 매핑</span><span class="sxs-lookup"><span data-stu-id="a30b1-102">Modeling and Mapping</span></span>
<span data-ttu-id="a30b1-103">Entity Framework에서 개념적 모델, 저장소 모델 및 응용 프로그램에 가장 적합 한 방식으로 두 모델 간의 매핑을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a30b1-103">In the Entity Framework, you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="a30b1-104">Visual Studio의 엔터티 데이터 모델 도구를 사용 하 여를 만들 수 있습니다. 데이터베이스나 모델이 변경 될 때 데이터베이스 또는 그래픽 모델의 [edmx 파일](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) 을 업데이트 한 다음 해당 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a30b1-104">The Entity Data Model Tools in Visual Studio allow you to create an .[edmx file](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="a30b1-105">Entity Framework 4.1부터는 Code First 개발을 통해 모델을 프로그램 방식으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a30b1-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="a30b1-106">Code First 개발에는 두 가지 다른 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a30b1-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="a30b1-107">두 경우 모두 개발자는 .NET Framewor 클래스 정의를 코딩하여 모델을 정의한 후 데이터 주석 또는 fluent API를 사용하여 추가 매핑 또는 구성을 선택적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a30b1-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="a30b1-108">자세한 내용은 [모델 만들기](/ef/ef6/modeling/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a30b1-108">For more information, see [Creating a Model](/ef/ef6/modeling/).</span></span>  
  
 <span data-ttu-id="a30b1-109">.NET Framework에 포함 된 EDM 생성기를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a30b1-109">You can also use the EDM Generator, which is included with the .NET Framework.</span></span> <span data-ttu-id="a30b1-110">EdmGen.exe 생성기는 기존 데이터 소스에서 .csdl, .ssdl 및 .msl 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a30b1-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="a30b1-111">또한 모델 및 매핑 콘텐츠를 수동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a30b1-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="a30b1-112">자세한 내용은 [EDM 생성기 (EdmGen.exe)](edm-generator-edmgen-exe.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a30b1-112">For more information, see [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md).</span></span>
