---
title: Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: 4b604502e0fea591460f30cae28b64ff1703da65
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589437"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a><span data-ttu-id="2ccf5-102">Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항</span><span class="sxs-lookup"><span data-stu-id="2ccf5-102">Considerations When Hosting an ActiveX Control on a Windows Form</span></span>
<span data-ttu-id="2ccf5-103">Windows Forms는 Windows Forms 컨트롤을 호스팅하도록 최적화되어 있지만 ActiveX 컨트롤을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-103">Although Windows Forms have been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="2ccf5-104">ActiveX 컨트롤을 사용하는 애플리케이션을 계획할 때 다음 사항을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-104">Keep the following considerations in mind when planning an application that uses ActiveX controls:</span></span>  
  
- <span data-ttu-id="2ccf5-105">**보안** 공용 언어 런타임이 코드 액세스 보안과 관련하여 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-105">**Security** The common language runtime has been enhanced with regard to code access security.</span></span> <span data-ttu-id="2ccf5-106">Windows Forms 기능이 있는 애플리케이션은 완전히 신뢰할 수 있는 환경에서 문제 없이 실행할 수 있으며, 대부분의 기능에 액세스할 수 있지만 부분적으로 신뢰할 수 있는 환경에서도 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-106">Applications featuring Windows Forms can run in a fully trusted environment without issue and in a semi-trusted environment with most of the functionality accessible.</span></span> <span data-ttu-id="2ccf5-107">Windows Forms 컨트롤은 브라우저에서 별다른 어려움 없이 간단하게 호스팅될 수 있지만,</span><span class="sxs-lookup"><span data-stu-id="2ccf5-107">Windows Forms controls can be hosted in a browser with no complications.</span></span> <span data-ttu-id="2ccf5-108">Windows Forms의 ActiveX 컨트롤은 향상된 보안 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-108">However, ActiveX controls on Windows Forms cannot take advantage of these security enhancements.</span></span> <span data-ttu-id="2ccf5-109">ActiveX 컨트롤을 실행 하려면으로 설정 되는 비관리 코드 권한이 있어야 합니다 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-109">Running an ActiveX control requires unmanaged code permission, which is set with the <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2ccf5-110">보안 및 비관리 코드 권한에 대 한 자세한 내용은 참조 하세요. <xref:System.Security.Permissions.SecurityPermissionAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-110">For more information about security and unmanaged code permission, see <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span></span>  
  
- <span data-ttu-id="2ccf5-111">**TCO(총 소유 비용)** Windows Form에 추가된 ActiveX 컨트롤은 해당 Windows Form과 함께 전부 배포되므로 만들어지는 파일의 크기가 상당히 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-111">**Total Cost of Ownership** ActiveX controls added to a Windows Form are deployed with that Windows Form in their entirety, which can add significantly to the size of the file(s) created.</span></span> <span data-ttu-id="2ccf5-112">또한 Windows Forms에서 ActiveX 컨트롤을 사용하려면 레지스트리에 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-112">Additionally, using ActiveX controls on Windows Forms requires writing to the registry.</span></span> <span data-ttu-id="2ccf5-113">이 작업은 레지스트리에 기록할 필요가 없는 Windows Forms 컨트롤에 비해 사용자의 컴퓨터를 간섭할 여지가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-113">This is more invasive to a user's computer than Windows Forms controls, which do not require this.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ccf5-114">ActiveX 컨트롤을 사용하려면 COM interop 래퍼를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-114">Working with an ActiveX control requires the use of a COM interop wrapper.</span></span> <span data-ttu-id="2ccf5-115">자세한 내용은 [Visual Basic 및 Visual C#의 COM 상호 운용성](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-115">For more information, see [COM Interoperability in Visual Basic and Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ccf5-116">ActiveX 컨트롤 가져오기에서 멤버 이름의 접두사는 경우 ActiveX 컨트롤의 멤버 이름에는.NET Framework에 정의 된 이름과 일치 하 **Ctl** 를 만들 때의 <xref:System.Windows.Forms.AxHost> 클래스를 파생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-116">If the name of a member of the ActiveX control matches a name defined in the .NET Framework, then the ActiveX Control Importer will prefix the member name with **Ctl** when it creates the <xref:System.Windows.Forms.AxHost> derived class.</span></span> <span data-ttu-id="2ccf5-117">예를 들어, ActiveX 컨트롤 이라는 멤버가 있으면 **레이아웃**, 이름이 **CtlLayout** AxHost 파생 클래스에서 때문에 **레이아웃** 이벤트 내에 정의 되어 합니다. NET 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="2ccf5-117">For example, if your ActiveX control has a member named **Layout**, it is renamed **CtlLayout** in the AxHost-derived class because the **Layout** event is defined within the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ccf5-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ccf5-118">See also</span></span>

- [<span data-ttu-id="2ccf5-119">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="2ccf5-119">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="2ccf5-120">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="2ccf5-120">Code Access Security</span></span>](../../misc/code-access-security.md)
- <span data-ttu-id="2ccf5-121">[여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2ccf5-121">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="2ccf5-122">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="2ccf5-122">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="2ccf5-123">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2ccf5-123">Windows Forms Controls</span></span>](index.md)
