---
title: 관리자를 위한 .NET Framework 배포 가이드
description: 관리자용 .NET 배포 가이드를 읽습니다. .NET 버전 4.5 및 해당 시스템 종속성을 네트워크 전체에 배포하려면 이 정보를 사용합니다.
ms.date: 04/10/2018
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
ms.openlocfilehash: d58eac4f21e4f1069ac392aacb4e9818831e914c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622655"
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="7f5de-104">관리자를 위한 .NET Framework 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="7f5de-104">.NET Framework Deployment Guide for Administrators</span></span>

<span data-ttu-id="7f5de-105">이 단계별 문서에서는 시스템 관리자가 Microsoft Endpoint Configuration Manager를 사용하여 .NET Framework 4.5 및 해당 시스템 종속성을 네트워크 전체에 배포할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-105">This step-by-step article describes how a system administrator can deploy the .NET Framework 4.5 and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="7f5de-106">이 문서에서는 .NET Framework 4의 최소 요구 사항이 모든 대상 클라이언트 컴퓨터에서 충족되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-106">This article assumes that all target client computers meet the minimum requirements for the .NET Framework.</span></span> <span data-ttu-id="7f5de-107">.NET Framework 4.5 설치를 위한 소프트웨어와 하드웨어 요구 사항 목록은 [시스템 요구 사항](../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-107">For a list of the software and hardware requirements for installing the .NET Framework 4.5, see [System Requirements](../get-started/system-requirements.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7f5de-108">.NET Framework 4.5, Configuration Manager 및 Active Directory를 비롯하여 이 문서에서 언급된 소프트웨어에는 각각 사용권 계약 내용이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-108">The software referenced in this document, including, without limitation, the .NET Framework 4.5, Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="7f5de-109">이 지침에서는 적절한 소프트웨어 라이선스로 이러한 사용권 계약 내용을 검토하고 이에 동의했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-109">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="7f5de-110">이 지침에서는 이러한 사용권 계약의 어떠한 내용도 배제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-110">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>
>
> <span data-ttu-id="7f5de-111">.NET Framework 지원의 자세한 내용은 Microsoft 지원 웹 사이트에서 [.NET Framework 공식 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-111">For information about support for the .NET Framework, see [.NET Framework official support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) on the Microsoft Support website.</span></span>

<span data-ttu-id="7f5de-112">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="7f5de-113">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="7f5de-113">The deployment process</span></span>](#the_deployment_process)
- [<span data-ttu-id="7f5de-114">.NET Framework 배포</span><span class="sxs-lookup"><span data-stu-id="7f5de-114">Deploying the .NET Framework</span></span>](#deploying_in_a_test_environment)
- [<span data-ttu-id="7f5de-115">컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="7f5de-115">Create a collection</span></span>](#creating_a_collection)
- [<span data-ttu-id="7f5de-116">패키지 및 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="7f5de-116">Create a package and program</span></span>](#creating_a_package)
- [<span data-ttu-id="7f5de-117">배포 지점 선택</span><span class="sxs-lookup"><span data-stu-id="7f5de-117">Select a distribution point</span></span>](#select_dist_point)
- [<span data-ttu-id="7f5de-118">패키지 배포</span><span class="sxs-lookup"><span data-stu-id="7f5de-118">Deploy the package</span></span>](#deploying_package)
- [<span data-ttu-id="7f5de-119">리소스</span><span class="sxs-lookup"><span data-stu-id="7f5de-119">Resources</span></span>](#resources)
- [<span data-ttu-id="7f5de-120">문제 해결</span><span class="sxs-lookup"><span data-stu-id="7f5de-120">Troubleshooting</span></span>](#troubleshooting)

<a name="the_deployment_process"></a>

## <a name="the-deployment-process"></a><span data-ttu-id="7f5de-121">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="7f5de-121">The deployment process</span></span>

<span data-ttu-id="7f5de-122">지원 인프라가 갖춰진 경우 Configuration Manager를 사용하여 .NET Framework 재배포 가능 패키지를 네트워크 상의 컴퓨터에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-122">When you have the supporting infrastructure in place, you use Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="7f5de-123">인프라 구축에는 컬렉션, 소프트웨어에 대한 패키지와 프로그램, 배포 지점, 배포의 5가지 주요 영역을 만들고 정의하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-123">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>

- <span data-ttu-id="7f5de-124">**컬렉션**은 .NET Framework가 배포되는 대상인 사용자, 사용자 그룹 또는 컴퓨터와 같은 Configuration Manager 리소스 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-124">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which the .NET Framework is deployed.</span></span> <span data-ttu-id="7f5de-125">자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager의 컬렉션 소개](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-125">For more information, see [Introduction to collections in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="7f5de-126">**패키지 및 프로그램**은 보통 클라이언트 컴퓨터에 설치할 소프트웨어 애플리케이션을 나타내지만, 개별 파일, 업데이트 또는 개별 명령까지도 들어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-126">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="7f5de-127">자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager의 패키지와 프로그램](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-127">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="7f5de-128">**배포 지점**은 클라이언트 컴퓨터에서 실행할 소프트웨어에 필요한 파일을 저장하는 Configuration Manager 사이트 시스템 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-128">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="7f5de-129">Configuration Manager 클라이언트가 소프트웨어 배포를 수신하고 처리할 때, 이 클라이언트는 배포 지점에 연결하여 소프트웨어와 연결된 콘텐츠를 다운로드하고 설치 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-129">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="7f5de-130">자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager의 콘텐츠 관리 기초 개념](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-130">For more information, see [Fundamental concepts for content management in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="7f5de-131">**배포**에서는 지정된 대상 컬렉션의 적절한 멤버에게 소프트웨어 패키지를 설치하라고 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-131">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f5de-132">이 항목의 절차에는 패키지와 프로그램을 만들고 배포하기 위한 일반적인 설정이 포함되어 있고, 가능한 모든 설정이 다루어지지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-132">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="7f5de-133">다른 Configuration Manager 배포 옵션은 [Configuration Manager 문서 라이브러리](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-133">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).</span></span>

<a name="deploying_in_a_test_environment"></a>

## <a name="deploying-the-net-framework"></a><span data-ttu-id="7f5de-134">.NET Framework 배포</span><span class="sxs-lookup"><span data-stu-id="7f5de-134">Deploying the .NET Framework</span></span>

<span data-ttu-id="7f5de-135">Configuration Manager를 사용하여 .NET Framework 4.5의 자동 설치를 배포할 수 있고, 이 경우 사용자는 설치 프로세스와 상호 작용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-135">You can use Configuration Manager to deploy a silent installation of the .NET Framework 4.5, where the users do not interact with the installation process.</span></span> <span data-ttu-id="7f5de-136">아래 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-136">Follow these steps:</span></span>

1. <span data-ttu-id="7f5de-137">[컬렉션을 만듭니다](#creating_a_collection).</span><span class="sxs-lookup"><span data-stu-id="7f5de-137">[Create a collection](#creating_a_collection).</span></span>

2. <span data-ttu-id="7f5de-138">[.NET Framework 재배포 가능 패키지와 프로그램을 만듭니다](#creating_a_package).</span><span class="sxs-lookup"><span data-stu-id="7f5de-138">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>

3. <span data-ttu-id="7f5de-139">[배포 지점을 선택합니다](#select_dist_point).</span><span class="sxs-lookup"><span data-stu-id="7f5de-139">[Select a distribution point](#select_dist_point).</span></span>

4. <span data-ttu-id="7f5de-140">[패키지를 배포합니다](#deploying_package).</span><span class="sxs-lookup"><span data-stu-id="7f5de-140">[Deploy the package](#deploying_package).</span></span>

<a name="creating_a_collection"></a>

### <a name="create-a-collection"></a><span data-ttu-id="7f5de-141">컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="7f5de-141">Create a collection</span></span>

<span data-ttu-id="7f5de-142">이 단계에서는 패키지와 프로그램을 배포할 컴퓨터를 선택하고 이런 컴퓨터를 디바이스 컬렉션으로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-142">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="7f5de-143">Configuration Manager에서 컬렉션을 만들려면 직접 멤버 자격 규칙(컬렉션 멤버를 수동으로 지정함) 또는 쿼리 규칙(사용자가 지정하는 기준을 바탕으로 Configuration Manager가 컬렉션 멤버를 결정함)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-143">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="7f5de-144">쿼리와 직접 규칙을 포함한 멤버 자격 규칙에 대한 자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager의 컬렉션 소개](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-144">For more information about membership rules, including queries and direct rules, see [Introduction to collections in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager Documentation Library.</span></span>

<span data-ttu-id="7f5de-145">컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7f5de-145">To create a collection:</span></span>

1. <span data-ttu-id="7f5de-146">Configuration Manager 콘솔에서 **자산 및 준수**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-146">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>

2. <span data-ttu-id="7f5de-147">**자산 및 준수** 작업 영역에서 **디바이스 컬렉션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-147">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>

3. <span data-ttu-id="7f5de-148">**만들기** 그룹의 **홈** 탭에서 **디바이스 컬렉션 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-148">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>

4. <span data-ttu-id="7f5de-149">**디바이스 컬렉션 만들기 마법사**의 **일반** 페이지에서 컬렉션 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-149">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>

5. <span data-ttu-id="7f5de-150">**찾아보기**를 선택하여 제한 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-150">Choose **Browse** to specify a limiting collection.</span></span>

6. <span data-ttu-id="7f5de-151">**멤버 자격 규칙** 페이지에서 **규칙 추가**를 선택한 다음 **직접 규칙**을 선택하여 **직접 멤버 자격 규칙 만들기 마법사**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-151">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="7f5de-152">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-152">Choose **Next**.</span></span>

7. <span data-ttu-id="7f5de-153">**리소스 검색** 페이지의 **리소스 클래스** 목록에서 **시스템 리소스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-153">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="7f5de-154">**특성 이름** 목록에서 **이름**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-154">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="7f5de-155">**값** 필드에 `%`를 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-155">In the **Value** field, enter `%`, and then choose **Next**.</span></span>

8. <span data-ttu-id="7f5de-156">**리소스 선택** 페이지에서 .NET Framework를 배포할 각 컴퓨터에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-156">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="7f5de-157">**다음**을 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-157">Choose **Next**, and then complete the wizard.</span></span>

9. <span data-ttu-id="7f5de-158">**디바이스 컬렉션 만들기 마법사**의 **멤버 자격 규칙** 페이지에서 **다음**을 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-158">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>

<a name="creating_a_package"></a>

### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="7f5de-159">.NET Framework 재배포 가능 패키지에 대한 프로그램과 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-159">Create a package and program for the .NET Framework redistributable package</span></span>

<span data-ttu-id="7f5de-160">다음 단계에서는 .NET Framework 재배포 가능 패키지를 수동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-160">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="7f5de-161">이 패키지에는 .NET Framework를 설치하기 위해 지정된 매개 변수와 패키지가 대상 컴퓨터에 배포될 시작 위치가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-161">The package contains the specified parameters for installing the .NET Framework and the location from where the package will be distributed to the target computers.</span></span>

<span data-ttu-id="7f5de-162">패키지를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7f5de-162">To create a package:</span></span>

1. <span data-ttu-id="7f5de-163">Configuration Manager 콘솔에서 **소프트웨어 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-163">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="7f5de-164">**소프트웨어 라이브러리** 작업 영역에서 **애플리케이션 관리**를 확장한 후 **패키지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-164">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="7f5de-165">**홈** 탭의 **만들기** 그룹에서 **패키지 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-165">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>

4. <span data-ttu-id="7f5de-166">**패키지 및 프로그램 만들기 마법사**의 **패키지** 페이지에서 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-166">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    - <span data-ttu-id="7f5de-167">이름: `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="7f5de-167">Name: `.NET Framework 4.5`</span></span>

    - <span data-ttu-id="7f5de-168">제조업체: `Microsoft`</span><span class="sxs-lookup"><span data-stu-id="7f5de-168">Manufacturer: `Microsoft`</span></span>

    - <span data-ttu-id="7f5de-169">Language:</span><span class="sxs-lookup"><span data-stu-id="7f5de-169">Language.</span></span> `English (US)`

5. <span data-ttu-id="7f5de-170">**이 패키지에 소스 파일이 포함됨**을 선택한 후 **찾아보기**를 선택하여 .NET Framework 설치 파일이 들어 있는 로컬 또는 네트워크 폴더를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-170">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="7f5de-171">폴더를 선택했으면 **확인**을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-171">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>

6. <span data-ttu-id="7f5de-172">마법사의 **프로그램 형식** 페이지에서 **표준 프로그램**을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-172">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>

7. <span data-ttu-id="7f5de-173">**패키지 및 프로그램 만들기 마법사**의 **프로그램** 페이지에서 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-173">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    1. <span data-ttu-id="7f5de-174">**이름:** `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="7f5de-174">**Name:** `.NET Framework 4.5`</span></span>

    2. <span data-ttu-id="7f5de-175">**명령줄:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT`(명령줄 옵션은 이러한 단계 뒤에 나오는 표에 설명되어 있음)</span><span class="sxs-lookup"><span data-stu-id="7f5de-175">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>

    3. <span data-ttu-id="7f5de-176">**실행:** **숨김**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-176">**Run:** Choose **Hidden**.</span></span>

    4. <span data-ttu-id="7f5de-177">**프로그램을 실행할 수 있음:** 사용자의 로그온 여부에 상관없이 프로그램을 실행할 수 있도록 지정하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-177">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>

8. <span data-ttu-id="7f5de-178">**요구 사항** 페이지에서 **다음**을 선택하여 기본값을 수락한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-178">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>

<span data-ttu-id="7f5de-179">다음 표에는 7단계에서 지정한 명령줄 옵션이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-179">The following table describes the command-line options specified in step 7.</span></span>

|<span data-ttu-id="7f5de-180">옵션</span><span class="sxs-lookup"><span data-stu-id="7f5de-180">Option</span></span>|<span data-ttu-id="7f5de-181">설명</span><span class="sxs-lookup"><span data-stu-id="7f5de-181">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="7f5de-182">**/q**</span><span class="sxs-lookup"><span data-stu-id="7f5de-182">**/q**</span></span>|<span data-ttu-id="7f5de-183">자동 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-183">Sets quiet mode.</span></span> <span data-ttu-id="7f5de-184">사용자 입력이 필요하지 않으며 아무런 출력도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-184">No user input is required, and no output is shown.</span></span>|
|<span data-ttu-id="7f5de-185">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="7f5de-185">**/norestart**</span></span>|<span data-ttu-id="7f5de-186">설치 프로그램이 자동으로 재부팅하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-186">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="7f5de-187">이 옵션을 사용하는 경우 Configuration Manager는 컴퓨터 다시 시작을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-187">If you use this option, Configuration Manager must handle the computer restart.</span></span>|
|<span data-ttu-id="7f5de-188">**/chainingpackage** *PackageName*</span><span class="sxs-lookup"><span data-stu-id="7f5de-188">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="7f5de-189">연결을 수행하는 패키지의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-189">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="7f5de-190">이 정보는 Microsoft CEIP(사용자 환경 개선 프로그램)에 등록한 사용자에 대한 다른 설치 세션 정보와 함께 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-190">This information is reported with other installation session information for those who have signed up for the Microsoft Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="7f5de-191">패키지 이름에 공백이 포함되어 있으면 **/chainingpackage "Chaining Product"** 와 같이 큰따옴표를 구분 기호로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-191">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|

<span data-ttu-id="7f5de-192">위 단계를 통해 .NET Framework 4.5라는 이름의 패키지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-192">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="7f5de-193">이 프로그램은 .NET Framework 4.5 자동 설치 프로그램을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-193">The program deploys a silent installation of the .NET Framework 4.5.</span></span> <span data-ttu-id="7f5de-194">자동 설치에서 사용자는 설치 프로세스와 상호 작용하지 않으며 연결 애플리케이션은 반환 코드를 캡처하고 재부팅을 처리해야 합니다. [설치 패키지에서 프로세스 진행 정보 가져오기](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-194">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).</span></span>

<a name="select_dist_point"></a>

### <a name="select-a-distribution-point"></a><span data-ttu-id="7f5de-195">배포 지점 선택</span><span class="sxs-lookup"><span data-stu-id="7f5de-195">Select a distribution point</span></span>

<span data-ttu-id="7f5de-196">서버에서 클라이언트 컴퓨터에 패키지와 프로그램을 배포하려면 먼저 사이트 시스템을 배포 지점으로 지정한 다음 배포 지점에 패키지를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-196">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>

<span data-ttu-id="7f5de-197">다음 단계에 따라 이전 섹션에서 만든 .NET Framework 4.5 패키지에 대한 배포 지점을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-197">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>

1. <span data-ttu-id="7f5de-198">Configuration Manager 콘솔에서 **소프트웨어 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-198">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="7f5de-199">**소프트웨어 라이브러리** 작업 영역에서 **애플리케이션 관리**를 확장한 후 **패키지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-199">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="7f5de-200">패키지 목록에서 이전 섹션에서 만든 **.NET Framework 4.5** 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-200">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>

4. <span data-ttu-id="7f5de-201">**홈** 탭의 **배포** 그룹에서 **콘텐츠 배포**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-201">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>

5. <span data-ttu-id="7f5de-202">**콘텐츠 배포 마법사**의 **일반** 탭에서 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-202">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>

6. <span data-ttu-id="7f5de-203">마법사의 **콘텐츠 대상** 페이지에서 **추가**를 선택한 후 **배포 지점**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-203">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>

7. <span data-ttu-id="7f5de-204">**배포 지점 추가** 대화 상자에서 패키지와 프로그램을 호스트하는 배포 지점을 선택한 후 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-204">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>

8. <span data-ttu-id="7f5de-205">마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-205">Complete the wizard.</span></span>

<span data-ttu-id="7f5de-206">이제 패키지에는 .NET Framework 4.5를 자동으로 배포하는 데 필요한 모든 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-206">The package now contains all the information you need to silently deploy the .NET Framework 4.5.</span></span> <span data-ttu-id="7f5de-207">패키지와 프로그램을 배포하기 전에 배포 지점에 .NET Framework 4.5가 설치되었는지 확인합니다. Configuration Manager 문서 라이브러리에서 [Configuration Manager에서 배포한 콘텐츠 모니터링](https://docs.microsoft.com/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed)의 "콘텐츠 상태 모니터링" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-207">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Content status monitoring" section of [Monitor content you distribute with Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) in the Configuration Manager Documentation Library.</span></span>

<a name="deploying_package"></a>

### <a name="deploy-the-package"></a><span data-ttu-id="7f5de-208">패키지 배포</span><span class="sxs-lookup"><span data-stu-id="7f5de-208">Deploy the package</span></span>

<span data-ttu-id="7f5de-209">.NET Framework 4.5 패키지와 프로그램을 배포하려면</span><span class="sxs-lookup"><span data-stu-id="7f5de-209">To deploy the .NET Framework 4.5 package and program:</span></span>

1. <span data-ttu-id="7f5de-210">Configuration Manager 콘솔에서 **소프트웨어 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-210">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="7f5de-211">**소프트웨어 라이브러리** 작업 영역에서 **애플리케이션 관리**를 확장한 후 **패키지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-211">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="7f5de-212">패키지 목록에서 **.NET Framework 4.5**로 명명하여 만든 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-212">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>

4. <span data-ttu-id="7f5de-213">**홈** 탭의 **배포** 그룹에서 **배포**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-213">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>

5. <span data-ttu-id="7f5de-214">**소프트웨어 배포 마법사**의 **일반** 페이지에서 **찾아보기**를 선택한 후 앞서 만든 컬렉션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-214">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="7f5de-215">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-215">Choose **Next**.</span></span>

6. <span data-ttu-id="7f5de-216">마법사의 **콘텐츠** 페이지에서 소프트웨어를 배포하려는 시작 지점이 표시되는지 확인하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-216">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>

7. <span data-ttu-id="7f5de-217">마법사의 **배포 설정** 페이지에서 **작업**이 **설치**로, **용도**가 **필수**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-217">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="7f5de-218">이렇게 하면 소프트웨어 패키지가 대상으로 지정된 컴퓨터에 필수적으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-218">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="7f5de-219">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-219">Choose **Next**.</span></span>

8. <span data-ttu-id="7f5de-220">마법사의 **일정** 페이지에서 .NET Framework를 설치하려는 시점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-220">On the **Scheduling** page of the wizard, specify when you want the .NET Framework to be installed.</span></span> <span data-ttu-id="7f5de-221">**새로 만들기**를 선택하여 설치 시간을 지정하거나, 사용자가 로그온하거나 로그오프할 때, 또는 최대한 빨리 소프트웨어를 설치하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-221">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="7f5de-222">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-222">Choose **Next**.</span></span>

9. <span data-ttu-id="7f5de-223">마법사의 **사용자 경험** 페이지에서 기본값을 사용하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-223">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="7f5de-224">프로덕션 환경에는 배포 일정에 대해 다른 선택 항목을 요구하는 정책이 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-224">Your production environment might have policies that require different selections for the deployment schedule.</span></span> <span data-ttu-id="7f5de-225">이러한 옵션에 대한 자세한 내용은 [보급 알림 이름 속성: 일정 탭](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-225">For information about these options, see [Advertisement Name Properties: Schedule Tab](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29).</span></span>

10. <span data-ttu-id="7f5de-226">마법사의 **배포 지점** 페이지에서 기본값을 사용하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-226">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>

11. <span data-ttu-id="7f5de-227">마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-227">Complete the wizard.</span></span> <span data-ttu-id="7f5de-228">**모니터링** 작업 영역의 **배포** 노드에서 배포의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-228">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>

<span data-ttu-id="7f5de-229">이제 패키지는 대상 컬렉션으로 배포되고 .NET Framework 4.5의 자동 설치가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-229">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="7f5de-230">.NET Framework 4.5 설치 오류 코드에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [반환 코드](#return_codes) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-230">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>

<a name="resources"></a>

## <a name="resources"></a><span data-ttu-id="7f5de-231">리소스</span><span class="sxs-lookup"><span data-stu-id="7f5de-231">Resources</span></span>

<span data-ttu-id="7f5de-232">.NET Framework 4.5 재배포 가능 패키지의 배포 테스트를 위한 인프라에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-232">For more information about the infrastructure for testing the deployment of the .NET Framework 4.5 redistributable package, see the following resources.</span></span>

<span data-ttu-id="7f5de-233">**Active Directory, DNS, DHCP:**</span><span class="sxs-lookup"><span data-stu-id="7f5de-233">**Active Directory, DNS, DHCP:**</span></span>

- [<span data-ttu-id="7f5de-234">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="7f5de-234">Active Directory Domain Services</span></span>](/windows/desktop/ad/active-directory-domain-services)

- [<span data-ttu-id="7f5de-235">DNS(Domain Name System)</span><span class="sxs-lookup"><span data-stu-id="7f5de-235">Domain Name System (DNS)</span></span>](/windows-server/networking/dns/dns-top)

- [<span data-ttu-id="7f5de-236">DHCP(Dynamic Host Configuration Protocol)</span><span class="sxs-lookup"><span data-stu-id="7f5de-236">Dynamic Host Configuration Protocol (DHCP)</span></span>](/windows-server/networking/technologies/dhcp/dhcp-top)

<span data-ttu-id="7f5de-237">**SQL Server 2008:**</span><span class="sxs-lookup"><span data-stu-id="7f5de-237">**SQL Server 2008:**</span></span>

- <span data-ttu-id="7f5de-238">[SQL Server 2008 설치(SQL Server 비디오)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="7f5de-238">[Installing SQL Server 2008 (SQL Server Video)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span></span>

- [<span data-ttu-id="7f5de-239">데이터베이스 관리자용 SQL Server 2008 보안 개요</span><span class="sxs-lookup"><span data-stu-id="7f5de-239">SQL Server 2008 Security Overview for Database Administrators</span></span>](https://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)

<span data-ttu-id="7f5de-240">**System Center 2012 Configuration Manager(관리 지점, 배포 지점):**</span><span class="sxs-lookup"><span data-stu-id="7f5de-240">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>

- [<span data-ttu-id="7f5de-241">System Center 2012 Configuration Manager의 사이트 관리</span><span class="sxs-lookup"><span data-stu-id="7f5de-241">Site Administration for System Center 2012 Configuration Manager</span></span>](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg681983%28v=technet.10%29)

- [<span data-ttu-id="7f5de-242">Configuration Manager 단일 사이트 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="7f5de-242">Configuration Manager Single Site Planning and Deployment</span></span>](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb680961%28v=technet.10%29)

<span data-ttu-id="7f5de-243">**Windows 컴퓨터용 System Center 2012 Configuration Manager 클라이언트:**</span><span class="sxs-lookup"><span data-stu-id="7f5de-243">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>

- [<span data-ttu-id="7f5de-244">System Center 2012 Configuration Manager용 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="7f5de-244">Deploying Clients for System Center 2012 Configuration Manager</span></span>](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699391%28v=technet.10%29)

<a name="troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="7f5de-245">문제 해결</span><span class="sxs-lookup"><span data-stu-id="7f5de-245">Troubleshooting</span></span>

### <a name="log-file-locations"></a><span data-ttu-id="7f5de-246">로그 파일 위치</span><span class="sxs-lookup"><span data-stu-id="7f5de-246">Log file locations</span></span>

<span data-ttu-id="7f5de-247">다음 로그 파일은 .NET Framework 설치 중에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-247">The following log files are generated during .NET Framework setup:</span></span>

- <span data-ttu-id="7f5de-248">%temp%\Microsoft .NET Framework *version*\*.txt</span><span class="sxs-lookup"><span data-stu-id="7f5de-248">%temp%\Microsoft .NET Framework *version*\*.txt</span></span>
- <span data-ttu-id="7f5de-249">%temp%\Microsoft .NET Framework *version*\*.html</span><span class="sxs-lookup"><span data-stu-id="7f5de-249">%temp%\Microsoft .NET Framework *version*\*.html</span></span>

<span data-ttu-id="7f5de-250">여기서 *version*은 설치 중인 .NET Framework의 버전(예: 4.5 또는 4.7.2)입니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-250">where *version* is the version of the .NET Framework that you're installing, such as 4.5 or 4.7.2.</span></span>

<span data-ttu-id="7f5de-251">.NET Framework 설치 명령에서 `/log` 명령줄 옵션을 사용하여 로그 파일이 작성되는 디렉터리를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-251">You can also specify the directory to which log files are written by using the `/log` command-line option in the .NET Framework installation command.</span></span> <span data-ttu-id="7f5de-252">자세한 내용은 [개발자를 위한 .NET Framework 배포 가이드](deployment-guide-for-developers.md#command-line-options)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-252">For more information, see [.NET Framework deployment guide for developers](deployment-guide-for-developers.md#command-line-options).</span></span>

<span data-ttu-id="7f5de-253">[로그 수집 도구](https://www.microsoft.com/download/details.aspx?id=12493)를 사용하여 .NET Framework 로그 파일을 수집하고 파일 크기를 줄여주는 압축된 캐비닛 파일(.cab)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-253">You can use the [log collection tool](https://www.microsoft.com/download/details.aspx?id=12493) to collect the .NET Framework log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>

<a name="return_codes"></a>

### <a name="return-codes"></a><span data-ttu-id="7f5de-254">반환 코드</span><span class="sxs-lookup"><span data-stu-id="7f5de-254">Return codes</span></span>

<span data-ttu-id="7f5de-255">다음 표에서는 .NET Framework 4.5 재배포 가능 설치 프로그램의 가장 일반적인 반환 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-255">The following table lists the most common return codes from the .NET Framework 4.5 redistributable installation program.</span></span> <span data-ttu-id="7f5de-256">반환 코드는 설치 관리자 버전에 관계없이 모두 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-256">The return codes are the same for all versions of the installer.</span></span>

<span data-ttu-id="7f5de-257">자세한 정보에 대한 링크는 다음 섹션인 [다운로드 오류 코드](#additional_error_codes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5de-257">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>

|<span data-ttu-id="7f5de-258">반환 코드</span><span class="sxs-lookup"><span data-stu-id="7f5de-258">Return code</span></span>|<span data-ttu-id="7f5de-259">설명</span><span class="sxs-lookup"><span data-stu-id="7f5de-259">Description</span></span>|
|-----------------|-----------------|
|<span data-ttu-id="7f5de-260">0</span><span class="sxs-lookup"><span data-stu-id="7f5de-260">0</span></span>|<span data-ttu-id="7f5de-261">설치되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-261">Installation completed successfully.</span></span>|
|<span data-ttu-id="7f5de-262">1602</span><span class="sxs-lookup"><span data-stu-id="7f5de-262">1602</span></span>|<span data-ttu-id="7f5de-263">사용자가 설치를 취소했습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-263">The user canceled installation.</span></span>|
|<span data-ttu-id="7f5de-264">1603</span><span class="sxs-lookup"><span data-stu-id="7f5de-264">1603</span></span>|<span data-ttu-id="7f5de-265">설치하는 동안 심각한 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-265">A fatal error occurred during installation.</span></span>|
|<span data-ttu-id="7f5de-266">1641</span><span class="sxs-lookup"><span data-stu-id="7f5de-266">1641</span></span>|<span data-ttu-id="7f5de-267">설치를 완료하려면 컴퓨터를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-267">A restart is required to complete the installation.</span></span> <span data-ttu-id="7f5de-268">이 메시지는 설치가 성공적으로 수행되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-268">This message indicates success.</span></span>|
|<span data-ttu-id="7f5de-269">3010</span><span class="sxs-lookup"><span data-stu-id="7f5de-269">3010</span></span>|<span data-ttu-id="7f5de-270">설치를 완료하려면 컴퓨터를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-270">A restart is required to complete the installation.</span></span> <span data-ttu-id="7f5de-271">이 메시지는 설치가 성공적으로 수행되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-271">This message indicates success.</span></span>|
|<span data-ttu-id="7f5de-272">5100</span><span class="sxs-lookup"><span data-stu-id="7f5de-272">5100</span></span>|<span data-ttu-id="7f5de-273">사용자 컴퓨터가 시스템 요구 사항을 충족하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5de-273">The user's computer does not meet system requirements.</span></span>|

<a name="additional_error_codes"></a>

### <a name="download-error-codes"></a><span data-ttu-id="7f5de-274">다운로드 오류 코드</span><span class="sxs-lookup"><span data-stu-id="7f5de-274">Download error codes</span></span>

- [<span data-ttu-id="7f5de-275">BITS(Background Intelligent Transfer Service) 오류 코드</span><span class="sxs-lookup"><span data-stu-id="7f5de-275">Background Intelligent Transfer Service (BITS) error codes</span></span>](/windows/desktop/Bits/bits-return-values)

- [<span data-ttu-id="7f5de-276">URL 모니커 오류 코드</span><span class="sxs-lookup"><span data-stu-id="7f5de-276">URL moniker error codes</span></span>](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145%28v=vs.85%29)

- [<span data-ttu-id="7f5de-277">WinHttp 오류 코드</span><span class="sxs-lookup"><span data-stu-id="7f5de-277">WinHttp error codes</span></span>](/windows/desktop/WinHttp/error-messages)

<span data-ttu-id="7f5de-278">기타 오류 코드</span><span class="sxs-lookup"><span data-stu-id="7f5de-278">Other error codes:</span></span>

- [<span data-ttu-id="7f5de-279">Windows Installer 오류 코드</span><span class="sxs-lookup"><span data-stu-id="7f5de-279">Windows Installer error codes</span></span>](/windows/desktop/msi/error-codes)

- <span data-ttu-id="7f5de-280">[Windows 업데이트 에이전트 결과 코드](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="7f5de-280">[Windows Update Agent result codes](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="7f5de-281">참조</span><span class="sxs-lookup"><span data-stu-id="7f5de-281">See also</span></span>

- [<span data-ttu-id="7f5de-282">개발자를 위한 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="7f5de-282">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)
- [<span data-ttu-id="7f5de-283">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f5de-283">System Requirements</span></span>](../get-started/system-requirements.md)
