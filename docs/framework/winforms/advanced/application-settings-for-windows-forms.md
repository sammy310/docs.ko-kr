---
title: Windows Forms에 대한 애플리케이션 설정
ms.date: 04/07/2017
f1_keywords:
- ClientApplicationSettings
helpviewer_keywords:
- application settings [Windows Forms]
- Windows Forms, application settings
ms.assetid: 64090a34-8556-4904-8ea0-20efe9f8c886
ms.openlocfilehash: 0cac4433ec9fe54721752c63d2b3b37f9d874c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779147"
---
# <a name="application-settings-for-windows-forms"></a><span data-ttu-id="4d33e-102">Windows Forms에 대한 애플리케이션 설정</span><span class="sxs-lookup"><span data-stu-id="4d33e-102">Application Settings for Windows Forms</span></span>
<span data-ttu-id="4d33e-103">Windows Forms의 응용 프로그램 설정 기능을 사용하면 클라이언트에서 사용자 지정 응용 프로그램과 사용자 기본 설정을 쉽게 만들고 저장 및 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-103">The Applications Settings feature of Windows Forms makes it easy to create, store, and maintain custom application and user preferences on the client.</span></span> <span data-ttu-id="4d33e-104">응용 프로그램 설정을 통해 데이터베이스 연결 문자열과 같은 응용 프로그램 데이터뿐 아니라 도구 모음 위치 및 가장 최근에 사용한 목록과 같은 사용자별 데이터도 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-104">With Application Settings, you can store not only application data such as database connection strings, but also user-specific data, such as toolbar positions and most-recently used lists.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d33e-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4d33e-105">In This Section</span></span>  
 [<span data-ttu-id="4d33e-106">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="4d33e-106">Application Settings Overview</span></span>](~/docs/framework/winforms/advanced/application-settings-overview.md)  
 <span data-ttu-id="4d33e-107">응용 프로그램 및 사용자를 대신하여 설정 데이터를 만들고 저장하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-107">Discusses how to create and store settings data on behalf of your application and your users.</span></span>  
  
 [<span data-ttu-id="4d33e-108">응용 프로그램 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="4d33e-108">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)  
 <span data-ttu-id="4d33e-109">응용 프로그램 설정 기능의 작동 방식을 설명하고 그룹화된 설정 및 설정 키와 같은 아키텍처의 고급 기능을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-109">Describes how the Application Settings feature works, and explores advanced features of the architecture such as grouped settings and settings keys.</span></span>  
  
 [<span data-ttu-id="4d33e-110">응용 프로그램 설정 특성</span><span class="sxs-lookup"><span data-stu-id="4d33e-110">Application Settings Attributes</span></span>](~/docs/framework/winforms/advanced/application-settings-attributes.md)  
 <span data-ttu-id="4d33e-111">응용 프로그램 설정 래퍼 클래스 또는 해당 설정 속성에 적용할 수 있는 특성을 나열하고 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-111">Lists and describes the attributes that can be applied to an application settings wrapper class or its settings properties.</span></span>  
  
 [<span data-ttu-id="4d33e-112">사용자 지정 컨트롤에 대한 응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="4d33e-112">Application Settings for Custom Controls</span></span>](~/docs/framework/winforms/advanced/application-settings-for-custom-controls.md)  
 <span data-ttu-id="4d33e-113">타사 응용 프로그램에서 호스트된 경우 사용자 지정 컨트롤이 응용 프로그램 설정을 유지할 수 있도록 하는 데 필요한 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-113">Discusses what must be done to give your custom controls the ability to persist application settings when hosted in third-party applications.</span></span>  
  
 [<span data-ttu-id="4d33e-114">방법: 응용 프로그램 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="4d33e-114">How to: Create Application Settings</span></span>](~/docs/framework/winforms/advanced/how-to-create-application-settings.md)  
 <span data-ttu-id="4d33e-115">응용 프로그램 세션 간에 유지되는 새 응용 프로그램 설정을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-115">Demonstrates creating new application settings that are persisted between application sessions.</span></span>  
  
 [<span data-ttu-id="4d33e-116">방법: 응용 프로그램 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4d33e-116">How to: Validate Application Settings</span></span>](~/docs/framework/winforms/advanced/how-to-validate-application-settings.md)  
 <span data-ttu-id="4d33e-117">응용 프로그램 설정이 유지되기 전에 유효성을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-117">Demonstrates validating application settings before they are persisted.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="4d33e-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4d33e-118">Related topics</span></span>

<span data-ttu-id="4d33e-119">[Windows Forms 구성 섹션](../../configure-apps/file-schema/winforms/index.md)  </span><span class="sxs-lookup"><span data-stu-id="4d33e-119">[Windows Forms Configuration Section](../../configure-apps/file-schema/winforms/index.md)  </span></span>  
<span data-ttu-id="4d33e-120">문서는.NET Framework 4.7부터 Windows Forms 응용 프로그램에서 높은 DPI를 사용 하도록 설정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-120">Documents the settings to enable High DPI support in Windows Forms Application starting with the .NET Framework 4.7.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d33e-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="4d33e-121">See also</span></span>

- [<span data-ttu-id="4d33e-122">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d33e-122">Windows Forms</span></span>](../index.md)
