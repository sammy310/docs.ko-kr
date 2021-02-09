---
description: '자세한 정보: 문제 해결: 텍스트 파일 읽기 및 쓰기(Visual Basic)'
title: '문제 해결: 텍스트 파일 읽기 및 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: 1c01f7673ef021759a9c1892f685aa90ef1acdf6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675340"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a><span data-ttu-id="d5273-103">문제 해결: 텍스트 파일 읽기 및 쓰기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5273-103">Troubleshooting: reading from and writing to text files (Visual Basic)</span></span>

<span data-ttu-id="d5273-104">이 항목에서는 텍스트 파일로 작업할 때 발생하는 일반적인 문제를 설명하고 각 문제에 대한 접근 방법을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-104">This topic discusses common problems encountered when working with text files and suggests an approach to each.</span></span>  
  
## <a name="common-problems"></a><span data-ttu-id="d5273-105">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="d5273-105">Common problems</span></span>  

 <span data-ttu-id="d5273-106">텍스트 파일로 작업할 때 발생하는 가장 일반적인 문제에는 보안 예외, 파일 인코딩, 잘못된 경로 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-106">The most common issues encountered when working with text files include security exceptions, file encodings, or invalid paths.</span></span>  
  
### <a name="security-exceptions"></a><span data-ttu-id="d5273-107">보안 예외</span><span class="sxs-lookup"><span data-stu-id="d5273-107">Security exceptions</span></span>  

 <span data-ttu-id="d5273-108">보안 오류가 발생하면 <xref:System.Security.SecurityException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-108">A <xref:System.Security.SecurityException> is thrown when a security error occurs.</span></span> <span data-ttu-id="d5273-109">이 예외는 사용자에게 필요한 사용 권한이 없어서 발생하는 경우가 많으며, 격리된 스토리지의 파일로 작업하거나 사용 권한을 추가하면 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-109">This is often a result of the user lacking necessary permissions, which may be solved by adding permissions or working with files in isolated storage.</span></span>  
  
### <a name="file-encodings"></a><span data-ttu-id="d5273-110">파일 인코딩</span><span class="sxs-lookup"><span data-stu-id="d5273-110">File encodings</span></span>  

 <span data-ttu-id="d5273-111">문자 인코딩이라고도 하는 파일 인코딩은 텍스트 처리 시 문자를 나타내는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-111">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="d5273-112">텍스트 파일의 예기치 않은 문자는 잘못된 인코딩에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-112">Unexpected characters in a text file may result from incorrect encoding.</span></span> <span data-ttu-id="d5273-113">처리할 수 있거나 없는 언어 문자를 기준으로 대부분의 파일에서 특정 인코딩이 다른 인코딩보다 선호될 수 있지만, 일반적으로 유니코드가 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-113">For most files, one encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span> <span data-ttu-id="d5273-114">자세한 내용은 [파일 인코딩](file-encodings.md) 및 <xref:System.Text.Encoding>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5273-114">For more information, see [File Encodings](file-encodings.md) and <xref:System.Text.Encoding>.</span></span>  
  
### <a name="incorrect-paths"></a><span data-ttu-id="d5273-115">잘못된 경로</span><span class="sxs-lookup"><span data-stu-id="d5273-115">Incorrect paths</span></span>  

 <span data-ttu-id="d5273-116">파일 경로, 특히 상대 경로를 구문 분석할 때 잘못된 데이터를 제공하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-116">When parsing file paths, particularly relative paths, it is easy to supply the wrong data.</span></span> <span data-ttu-id="d5273-117">올바른 경로를 제공하면 많은 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5273-117">Many problems can be corrected by making sure you are supplying the correct path.</span></span> <span data-ttu-id="d5273-118">자세한 내용은 [방법: 파일 경로의 구문 분석](how-to-parse-file-paths.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5273-118">For more information, see [How to: Parse File Paths](how-to-parse-file-paths.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5273-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5273-119">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [<span data-ttu-id="d5273-120">파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="d5273-120">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="d5273-121">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="d5273-121">Writing to Files</span></span>](writing-to-files.md)
- [<span data-ttu-id="d5273-122">TextFieldParser 개체를 사용하여 텍스트 파일 구문 분석</span><span class="sxs-lookup"><span data-stu-id="d5273-122">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)
