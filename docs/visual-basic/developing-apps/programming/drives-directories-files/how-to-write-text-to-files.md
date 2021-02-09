---
description: '자세한 정보: 방법: Visual Basic에서 파일에 텍스트 쓰기'
title: '방법: 파일에 텍스트 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic]
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
ms.openlocfilehash: 3f94999c1d20002074ecf57577d3402c350248ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797343"
---
# <a name="how-to-write-text-to-files-in-visual-basic"></a><span data-ttu-id="8369b-103">방법: Visual Basic에서 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="8369b-103">How to: Write Text to Files in Visual Basic</span></span>

<span data-ttu-id="8369b-104"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 메서드를 사용하여 파일에 텍스트를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to write text to files.</span></span> <span data-ttu-id="8369b-105">지정한 파일이 없으면 새로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-105">If the specified file does not exist, it is created.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="8369b-106">프로시저</span><span class="sxs-lookup"><span data-stu-id="8369b-106">Procedure</span></span>  
  
#### <a name="to-write-text-to-a-file"></a><span data-ttu-id="8369b-107">파일에 텍스트를 쓰려면</span><span class="sxs-lookup"><span data-stu-id="8369b-107">To write text to a file</span></span>  
  
- <span data-ttu-id="8369b-108">파일과 쓸 텍스트를 지정하여 `WriteAllText` 메서드를 통해 파일에 텍스트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-108">Use the `WriteAllText` method to write text to a file, specifying the file and text to be written.</span></span> <span data-ttu-id="8369b-109">이 예제에서는 `test.txt`라는 파일에 `"This is new text."` 줄을 쓰고 파일에 있는 기존 텍스트에 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-109">This example writes the line `"This is new text."` to the file named `test.txt`, appending the text to any existing text in the file.</span></span>  
  
     [!code-vb[VbFileIOWrite#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#3)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a><span data-ttu-id="8369b-110">일련의 문자열을 파일에 쓰려면</span><span class="sxs-lookup"><span data-stu-id="8369b-110">To write a series of strings to a file</span></span>  
  
- <span data-ttu-id="8369b-111">문자열 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-111">Loop through the string collection.</span></span> <span data-ttu-id="8369b-112">대상 파일 및 추가할 문자열을 지정하고 `append`를 `True`로 설정하여 `WriteAllText` 메서드를 통해 파일에 텍스트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-112">Use the `WriteAllText` method to write text to a file, specifying the target file and string to be added and setting `append` to `True`.</span></span>  
  
     <span data-ttu-id="8369b-113">이 예제에서는 `Documents and Settings` 디렉터리에 있는 파일 이름을 `FileList.txt`에 쓰고, 가독성을 높이기 위해 각 이름 사이에 캐리지 리턴을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-113">This example writes the names of the files in the `Documents and Settings` directory to `FileList.txt`, inserting a carriage return between each for better readability.</span></span>  
  
     [!code-vb[VbFileIOWrite#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#4)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8369b-114">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8369b-114">Robust Programming</span></span>  

 <span data-ttu-id="8369b-115">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="8369b-116">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 디바이스 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="8369b-116">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="8369b-117">경로가 `Nothing` 이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="8369b-117">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="8369b-118">`File`이 존재하지 않는 경로를 가리키는 경우(<xref:System.IO.FileNotFoundException> 또는 <xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="8369b-118">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="8369b-119">다른 프로세스에서 파일을 사용 중이거나 I/O 오류가 발생한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="8369b-119">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="8369b-120">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="8369b-120">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="8369b-121">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="8369b-121">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="8369b-122">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="8369b-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="8369b-123">디스크가 꽉 찼고 `WriteAllText`에 대한 호출에 실패한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="8369b-123">The disk is full, and the call to `WriteAllText` fails (<xref:System.IO.IOException>).</span></span>  
  
 <span data-ttu-id="8369b-124">부분 신뢰 컨텍스트에서 실행하는 경우 권한 부족으로 인해 코드에서 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8369b-124">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="8369b-125">자세한 내용은 [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8369b-125">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8369b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8369b-126">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- [<span data-ttu-id="8369b-127">방법: 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="8369b-127">How to: Read from Text Files</span></span>](how-to-read-from-text-files.md)
