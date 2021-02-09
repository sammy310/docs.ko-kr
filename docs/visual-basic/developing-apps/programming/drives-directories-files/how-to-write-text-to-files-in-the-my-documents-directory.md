---
description: '자세한 정보: 방법: Visual Basic에서 내 문서 디렉터리의 파일에 텍스트 쓰기'
title: '방법: 내 문서 디렉터리의 파일에 텍스트 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: da7472e9d8d4c39509dda814a18e7c0149236eeb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797369"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="d2a69-103">방법: Visual Basic에서 내 문서 디렉터리의 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="d2a69-103">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>

<span data-ttu-id="d2a69-104">`My.Computer.FileSystem.SpecialDirectories` 개체를 사용하면 **MyDocuments** 디렉터리 등의 특수 디렉터리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-104">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="d2a69-105">프로시저</span><span class="sxs-lookup"><span data-stu-id="d2a69-105">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="d2a69-106">내 문서 디렉터리에 새 텍스트 파일을 쓰려면</span><span class="sxs-lookup"><span data-stu-id="d2a69-106">To write new text files in the My Documents directory</span></span>  
  
1. <span data-ttu-id="d2a69-107">`My.Computer.FileSystem.SpecialDirectories.MyDocuments` 속성을 사용하여 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-107">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="d2a69-108">`WriteAllText` 메서드를 사용하여 지정한 파일에 텍스트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-108">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="d2a69-109">예제</span><span class="sxs-lookup"><span data-stu-id="d2a69-109">Example</span></span>  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d2a69-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d2a69-110">Compiling the Code</span></span>  

 <span data-ttu-id="d2a69-111">`test.txt`를 쓰려는 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-111">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d2a69-112">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d2a69-112">Robust Programming</span></span>  

 <span data-ttu-id="d2a69-113">이 코드는 파일에 텍스트를 쓸 때 발생할 수 있는 모든 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-113">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="d2a69-114">유효한 파일 이름에 대한 사용자 선택 항목을 제한하는 [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) 및 [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms) 구성 요소와 같은 Windows Forms 컨트롤을 사용하여 예외 발생 가능성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-114">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) and the [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="d2a69-115">그러나 이러한 컨트롤을 사용해도 예외가 완전히 방지되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-115">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="d2a69-116">사용자가 파일을 선택한 시간과 코드가 실행되는 시간 사이에 파일 시스템이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-116">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="d2a69-117">따라서 파일 작업 시에는 거의 항상 예외 처리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-117">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d2a69-118">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="d2a69-118">.NET Framework Security</span></span>  

 <span data-ttu-id="d2a69-119">부분 신뢰 컨텍스트에서 실행하는 경우 권한 부족으로 인해 코드에서 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-119">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="d2a69-120">자세한 내용은 [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a69-120">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="d2a69-121">이 예제에서는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-121">This example creates a new file.</span></span> <span data-ttu-id="d2a69-122">애플리케이션에서 파일을 만들어야 하는 경우 해당 애플리케이션에 폴더에 대한 만들기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-122">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="d2a69-123">권한은 액세스 제어 목록을 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-123">Permissions are set using access control lists.</span></span> <span data-ttu-id="d2a69-124">파일이 이미 있는 경우에는 애플리케이션에 더 낮은 권한인 쓰기 권한만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-124">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="d2a69-125">가능한 경우 배포하는 동안 파일을 만들고, 폴더에 대한 만들기 권한 대신 단일 파일에 대한 읽기 권한만 부여하는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-125">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="d2a69-126">또한 루트 폴더나 **Program Files** 폴더보다 사용자 폴더에 데이터를 쓰는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a69-126">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="d2a69-127">자세한 내용은 [ACL 기술 개요](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a69-127">For more information, see [ACL Technology Overview](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a69-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2a69-128">See also</span></span>

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
