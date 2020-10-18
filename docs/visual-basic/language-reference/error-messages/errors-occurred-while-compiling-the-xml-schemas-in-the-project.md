---
title: 프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생했습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 747c2c8cb1e5dc3d4fcae86a9acf84446c4e59c9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162039"
---
# <a name="bc36810-errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="f1d76-102">BC36810: 프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-102">BC36810: Errors occurred while compiling the XML schemas in the project</span></span>

<span data-ttu-id="f1d76-103">프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="f1d76-104">따라서 XML IntelliSense를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-104">Because of this, XML IntelliSense is not available.</span></span>

 <span data-ttu-id="f1d76-105">프로젝트에 포함 된 XSD (XML 스키마 정의) 스키마에 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="f1d76-106">이 오류는 프로젝트에 대 한 기존 XSD 스키마 집합과 충돌 하는 XSD 스키마 (.xsd) 파일을 추가 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>

 <span data-ttu-id="f1d76-107">**오류 ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="f1d76-107">**Error ID:** BC36810</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f1d76-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f1d76-108">To correct this error</span></span>

- <span data-ttu-id="f1d76-109">**오류 목록** 창에서 해당 경고를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="f1d76-110">Visual Basic는 XSD 파일에서 경고 소스인 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="f1d76-111">XSD 스키마의 오류를 수정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f1d76-111">Correct the error in the XSD schema.</span></span>

- <span data-ttu-id="f1d76-112">필요한 모든 XSD 스키마 (.xsd) 파일이 프로젝트에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="f1d76-113">**솔루션 탐색기**에서 .xsd 파일을 보려면 [ **프로젝트** ] 메뉴에서 [ **모든 파일 표시** ]를 클릭 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="f1d76-114">.Xsd 파일을 마우스 오른쪽 단추로 클릭 한 다음 **프로젝트에 포함** 을 클릭 하 여 프로젝트에 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>

- <span data-ttu-id="f1d76-115">XML to Schema 마법사를 사용 하는 경우 동일한 소스에서 두 번 이상 스키마를 유추 하는 경우이 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="f1d76-116">이 경우 프로젝트에서 기존 XSD 스키마 파일을 제거 하 고 스키마 항목 템플릿에 새 XML을 추가한 다음 프로젝트에 적용 가능한 모든 XML 원본을 사용 하 여 XML 스키마 마법사를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>

- <span data-ttu-id="f1d76-117">XSD 스키마에서 오류가 식별 되지 않으면 XML 컴파일러에 자세한 오류 메시지를 제공 하는 데 충분 한 정보가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="f1d76-118">프로젝트에 포함 된 .xsd 파일에 대 한 XML 네임 스페이스가 Visual Studio의 XML 스키마 집합에 대해 식별 된 xml 네임 스페이스와 일치 하는지 확인 하는 경우 자세한 오류 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d76-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1d76-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1d76-119">See also</span></span>

- [<span data-ttu-id="f1d76-120">오류 목록 창</span><span class="sxs-lookup"><span data-stu-id="f1d76-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="f1d76-121">XML</span><span class="sxs-lookup"><span data-stu-id="f1d76-121">XML</span></span>](../../programming-guide/language-features/xml/index.md)
