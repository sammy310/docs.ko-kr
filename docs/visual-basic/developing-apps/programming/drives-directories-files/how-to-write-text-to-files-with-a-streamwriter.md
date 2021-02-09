---
description: '자세한 정보: 방법: Visual Basic에서 StreamWriter를 사용하여 파일에 텍스트 쓰기'
title: '방법: StreamWriter를 사용하여 파일에 텍스트 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
ms.openlocfilehash: d5528d0b5e7de40062558d29c0d3bebc227583a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797356"
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="a9eb0-103">방법: Visual Basic에서 StreamWriter를 사용하여 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="a9eb0-103">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>

<span data-ttu-id="a9eb0-104">이 예제에서는 `My.Computer.FileSystem.OpenTextFileWriter` 메서드를 사용하여 <xref:System.IO.StreamWriter> 개체를 열고 이 개체를 사용하여 <xref:System.IO.StreamWriter> 클래스의 <xref:System.IO.TextWriter.WriteLine%2A> 메서드로 텍스트 파일에 문자열을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a9eb0-104">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9eb0-105">예제</span><span class="sxs-lookup"><span data-stu-id="a9eb0-105">Example</span></span>  

 [!code-vb[VbFileIOWrite#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#5)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a9eb0-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a9eb0-106">Robust Programming</span></span>  

 <span data-ttu-id="a9eb0-107">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a9eb0-107">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="a9eb0-108">파일이 있지만 읽기 전용인 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="a9eb0-108">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="a9eb0-109">디스크가 꽉 찬 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="a9eb0-109">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="a9eb0-110">경로 이름이 너무 긴 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="a9eb0-110">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a9eb0-111">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="a9eb0-111">.NET Framework Security</span></span>  

 <span data-ttu-id="a9eb0-112">이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a9eb0-112">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="a9eb0-113">애플리케이션에서 파일을 만들어야 하는 경우 해당 애플리케이션에 폴더에 대한 `Create` 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9eb0-113">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="a9eb0-114">파일이 이미 있는 경우 애플리케이션에 더 낮은 권한인 `Write` 권한만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9eb0-114">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="a9eb0-115">가능한 경우 배포하는 동안 파일을 만들고, 폴더에 대한 `Create` 권한 대신 단일 파일에 대해 `Read` 권한만 부여하는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="a9eb0-115">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9eb0-116">참조</span><span class="sxs-lookup"><span data-stu-id="a9eb0-116">See also</span></span>

- <xref:System.IO.StreamWriter>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- [<span data-ttu-id="a9eb0-117">방법: 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="a9eb0-117">How to: Read from Text Files</span></span>](how-to-read-from-text-files.md)
- [<span data-ttu-id="a9eb0-118">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="a9eb0-118">Writing to Files</span></span>](writing-to-files.md)
