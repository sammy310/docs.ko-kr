---
description: '자세한 정보: 방법: Visual Basic에서 파일 업로드'
title: '방법: 파일 업로드'
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: d38820cda6a143cf3f06bf6a2ca72cba5a9f3aef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675405"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="a323f-103">방법: Visual Basic에서 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="a323f-103">How to: Upload a File in Visual Basic</span></span>

<span data-ttu-id="a323f-104"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> 메서드는 파일을 업로드하고 원격 위치에 저장하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a323f-104">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="a323f-105">`ShowUI` 매개 변수를 `True`로 설정하면 업로드 진행률을 표시하고 사용자가 작업을 취소할 수 있도록 하는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a323f-105">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="a323f-106">파일을 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="a323f-106">To upload a file</span></span>  
  
- <span data-ttu-id="a323f-107">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI(Uniform Resource Identifier)로 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다. 이 예제에서는 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a323f-107">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     [!code-vb[VbResourceTasks#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#6)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="a323f-108">파일을 업로드하고 작업 진행률을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="a323f-108">To upload a file and show the progress of the operation</span></span>  
  
- <span data-ttu-id="a323f-109">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI로 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a323f-109">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="a323f-110">이 예제에서는 사용자 이름 또는 암호를 제공하지 않고 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드하며, 업로드 진행률을 표시하고, 시간 제한 간격으로 500밀리초가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a323f-110">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     [!code-vb[VbResourceTasks#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#7)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="a323f-111">사용자 이름 및 암호를 제공하여 파일을 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="a323f-111">To upload a file, supplying a user name and password</span></span>  
  
- <span data-ttu-id="a323f-112">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI로 지정하고 사용자 이름 및 암호를 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a323f-112">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="a323f-113">이 예제에서는 사용자 이름 `anonymous` 및 빈 암호를 제공하여 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a323f-113">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     [!code-vb[VbResourceTasks#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a323f-114">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a323f-114">Robust Programming</span></span>  

 <span data-ttu-id="a323f-115">다음 조건에서는 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a323f-115">The following conditions may throw an exception:</span></span>  
  
- <span data-ttu-id="a323f-116">로컬 파일 경로가 잘못된 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="a323f-116">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="a323f-117">인증에 실패한 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="a323f-117">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="a323f-118">연결 시간이 초과된 경우(<xref:System.TimeoutException>)</span><span class="sxs-lookup"><span data-stu-id="a323f-118">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a323f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a323f-119">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [<span data-ttu-id="a323f-120">방법: 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="a323f-120">How to: Download a File</span></span>](how-to-download-a-file.md)
- [<span data-ttu-id="a323f-121">방법: 파일 경로 구문 분석</span><span class="sxs-lookup"><span data-stu-id="a323f-121">How to: Parse File Paths</span></span>](../drives-directories-files/how-to-parse-file-paths.md)
