---
title: 컨트롤
description: Windows Form 컨트롤을 추가 및 배치 하는 방법을 알아봅니다. 디자이너에서 컨트롤을 조작 하 고 런타임에 동적으로 컨트롤을 추가 하는 코드를 작성할 수도 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls
- controls [Windows Forms]
- Windows Forms controls, about Windows Forms controls
ms.assetid: f050de8f-4ebd-4042-94b8-edf9a1dbd52a
ms.openlocfilehash: 9ca4a2a1205663ae0ff4537a58cc1991a15da5d8
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324034"
---
# <a name="windows-forms-controls"></a><span data-ttu-id="05424-104">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="05424-104">Windows Forms controls</span></span>

<span data-ttu-id="05424-105">Windows Forms 애플리케이션의 사용자 인터페이스를 디자인하고 수정할 때는 컨트롤을 추가하고 정렬하고 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05424-105">As you design and modify the user interface of your Windows Forms applications, you will need to add, align, and position controls.</span></span> <span data-ttu-id="05424-106">컨트롤은 폼 개체에 포함된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="05424-106">Controls are objects that are contained within form objects.</span></span> <span data-ttu-id="05424-107">각 컨트롤 형식은 컨트롤을 특정 목적에 적합하게 만들어주는 자체적인 속성, 메서드 및 이벤트 집합을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="05424-107">Each type of control has its own set of properties, methods, and events that make it suitable for a particular purpose.</span></span> <span data-ttu-id="05424-108">디자이너에서 컨트롤을 조작하고 런타임에 동적으로 컨트롤을 추가하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05424-108">You can manipulate controls in the designer and write code to add controls dynamically at run time.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="05424-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="05424-109">In this section</span></span>

<span data-ttu-id="05424-110">[Windows Forms에 컨트롤 배치](putting-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="05424-110">[Putting Controls on Windows Forms](putting-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="05424-111">폼의 컨트롤 배치와 관련된 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05424-111">Provides links related to putting controls on forms.</span></span>

<span data-ttu-id="05424-112">[Windows Forms에서 컨트롤 정렬](how-to-align-multiple-controls-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="05424-112">[Arranging Controls on Windows Forms](how-to-align-multiple-controls-on-windows-forms.md)</span></span>\
<span data-ttu-id="05424-113">폼에서 컨트롤을 정렬 하는 것과 관련 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="05424-113">Articles related to arranging controls on forms.</span></span>

<span data-ttu-id="05424-114">[개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span><span class="sxs-lookup"><span data-stu-id="05424-114">[Labeling Individual Windows Forms Controls and Providing Shortcuts to Them](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)</span></span>\
<span data-ttu-id="05424-115">사용 하는 바로 가기 키, 컨트롤의 텍스트 레이블 및 보조키에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05424-115">Describes the uses of keyboard shortcuts, text labels on controls, and modifier keys.</span></span>

<span data-ttu-id="05424-116">[Windows Forms에서 사용할 컨트롤](controls-to-use-on-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="05424-116">[Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md)</span></span>\
<span data-ttu-id="05424-117">Windows Forms에서 작동하는 컨트롤 및 각 컨트롤로 수행할 수 있는 기본 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="05424-117">Lists the controls that work with Windows Forms, and basic things you can accomplish with each control.</span></span>

<span data-ttu-id="05424-118">[.NET Framework를 사용 하 여 사용자 지정 Windows Forms 컨트롤 개발](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="05424-118">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="05424-119">사용자 지정 Windows Forms 컨트롤을 개발하는 데 도움이 되는 배경 정보 및 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05424-119">Provides background information and samples to help users develop custom Windows Forms controls.</span></span>

<span data-ttu-id="05424-120">[디자인 타임에 Windows Forms 컨트롤 개발](developing-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="05424-120">[Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="05424-121">디자인 및 상속을 통해 사용자 지정 컨트롤을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05424-121">Describes techniques for creating custom controls through design and inheritance.</span></span>

## <a name="related-sections"></a><span data-ttu-id="05424-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="05424-122">Related sections</span></span>

<span data-ttu-id="05424-123">[클라이언트 응용 프로그램](../../develop-client-apps.md)</span><span class="sxs-lookup"><span data-stu-id="05424-123">[Client Applications](../../develop-client-apps.md)</span></span>\
<span data-ttu-id="05424-124">Windows 기반 애플리케이션을 개발하는 방법을 개괄적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05424-124">Provides an overview of developing Windows-based applications.</span></span>
