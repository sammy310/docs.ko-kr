---
title: My.Application, My.Computer 및 My.User를 사용한 작업 수행
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 55961d6857b690fc2726f541df8a5497a3207928
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411696"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="cc7da-102">My.Application, My.Computer 및 My.User를 사용한 작업 수행(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc7da-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>

<span data-ttu-id="cc7da-103">`My` 개체는 `My.Application`(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer`(<xref:Microsoft.VisualBasic.Devices.Computer>) 및 `My.User`(<xref:Microsoft.VisualBasic.ApplicationServices.User>)의 세 가지 중앙 개체 중 하나로, 이를 통해 정보 및 일반적으로 사용되는 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="cc7da-104">이러한 개체를 사용하여 현재 애플리케이션, 애플리케이션이 설치된 컴퓨터 또는 애플리케이션의 현재 사용자와 관련된 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="cc7da-105">My.Application, My.Computer 및 My.User</span><span class="sxs-lookup"><span data-stu-id="cc7da-105">My.Application, My.Computer, and My.User</span></span>  

 <span data-ttu-id="cc7da-106">다음 예제에서는 `My`를 사용하여 정보를 검색하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="cc7da-107">정보를 검색하는 것 외에도, 이러한 세 가지 개체를 통해 노출된 멤버를 사용하여 해당 개체와 관련된 메서드를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="cc7da-108">예를 들어 다양한 메서드에 액세스하여 파일을 조작하거나 `My.Computer`를 통해 레지스트리를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="cc7da-109">파일 I/O는 파일, 디렉터리 및 드라이브 조작을 위한 다양한 메서드 및 속성을 포함하는 `My`를 통해 훨씬 쉽고 빠르게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="cc7da-110"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser> 개체를 사용하면 구분되거나 고정 너비 필드가 있는 크고 구조화된 파일에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="cc7da-111">이 예제에서는 `TextFieldParser` `reader`를 열고 이를 사용하여 `C:\TestFolder1\test1.txt`에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="cc7da-112">`My.Application`을 사용하면 애플리케이션의 문화권을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="cc7da-113">다음 예제에서는 이 메서드를 호출할 수 있는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc7da-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="cc7da-114">참조</span><span class="sxs-lookup"><span data-stu-id="cc7da-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="cc7da-115">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="cc7da-115">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
