---
title: '방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시'
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 86ec8f9ae76f010ebbc3be393d8d257ba5cfc6b6
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834621"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="a6cea-102">방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="a6cea-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>

<span data-ttu-id="a6cea-103">컨트롤을 개발 하 고 배포 하는 경우 **도구 상자** 를 마우스 오른쪽 단추로 클릭 하 고 **항목 선택**을 선택 하면 표시 되는 Visual Studio의 **도구 상자 항목 선택** 대화 상자에 해당 컨트롤이 표시 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cea-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box of Visual Studio, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="a6cea-104">AssemblyFoldersEx 등록 프로시저를 사용 하 여이 대화 상자에 표시 되도록 컨트롤을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cea-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>

<span data-ttu-id="a6cea-105">도구 상자 항목 선택 대화 상자에 컨트롤을 표시 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cea-105">To display your control in the Choose Toolbox Items dialog box:</span></span>

- <span data-ttu-id="a6cea-106">컨트롤 어셈블리를 전역 어셈블리 캐시에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cea-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="a6cea-107">자세한 내용은 [방법: 글로벌 어셈블리 캐시에 어셈블리 설치](../../app-domains/install-assembly-into-gac.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6cea-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/install-assembly-into-gac.md).</span></span>

  <span data-ttu-id="a6cea-108">또는</span><span class="sxs-lookup"><span data-stu-id="a6cea-108">-or-</span></span>

- <span data-ttu-id="a6cea-109">AssemblyFoldersEx 등록 프로시저를 사용 하 여 컨트롤 및 연결 된 디자인 타임 어셈블리를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6cea-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="a6cea-110">AssemblyFoldersEx은 타사 공급 업체가 지 원하는 각 프레임 워크 버전에 대 한 경로를 저장 하는 레지스트리 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a6cea-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="a6cea-111">디자인 타임 확인은이 레지스트리 위치를 확인 하 여 참조 어셈블리를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cea-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="a6cea-112">레지스트리 스크립트는 도구 상자에 표시할 컨트롤을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6cea-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6cea-113">참조</span><span class="sxs-lookup"><span data-stu-id="a6cea-113">See also</span></span>

- [<span data-ttu-id="a6cea-114">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="a6cea-114">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="a6cea-115">방법: 글로벌 어셈블리 캐시에 어셈블리 설치</span><span class="sxs-lookup"><span data-stu-id="a6cea-115">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/install-assembly-into-gac.md)
- [<span data-ttu-id="a6cea-116">연습: 사용자 지정 구성 요소를 사용 하 여 도구 상자 자동 채우기</span><span class="sxs-lookup"><span data-stu-id="a6cea-116">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
