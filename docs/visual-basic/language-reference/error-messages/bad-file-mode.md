---
title: 파일 모드가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: d3d0ebd003f178567ec9e9b19d6baccb8bc15f60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819985"
---
# <a name="bad-file-mode"></a><span data-ttu-id="89ad2-102">파일 모드가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-102">Bad file mode</span></span>
<span data-ttu-id="89ad2-103">파일 콘텐츠를 조작에 사용 된 문이 파일이 열린 모드에 적합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="89ad2-104">이 오류가 발생하는 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="89ad2-105">A `FilePutObject` 또는 `FileGetObject` 문을 순차적 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="89ad2-106">A `Print` 이외의 액세스 모드에 대 한 열린 파일을 지정 하는 문을 `Output` 또는 `Append`합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="89ad2-107">`Input` 이외의 액세스 모드에 대 한 열린 파일을 지정 하는 문 `Input`</span><span class="sxs-lookup"><span data-stu-id="89ad2-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="89ad2-108">읽기 전용 파일에 기록 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89ad2-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="89ad2-109">To correct this error</span></span>  
  
-   <span data-ttu-id="89ad2-110">했는지 `FilePutObject` 하 고 `FileGetObject` 파일 열기에 대 한 참조만 `Random` 또는 `Binary` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="89ad2-111">했는지 `Print` 에 대 한 열린 파일을 지정 `Output` 또는 `Append` 액세스 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="89ad2-112">그렇지 않은 경우 다른 문을 사용 하 여 파일에서 데이터를 배치 하거나 적절 한 모드에서 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="89ad2-113">했는지 `Input` 열린 파일을 지정 `Input`합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="89ad2-114">그렇지 않은 경우 다른 문을 사용 하 여 데이터 파일에 배치 하거나 적절 한 모드에서 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="89ad2-115">읽기 전용 파일에 작성 하는 경우 파일의 읽기/쓰기 상태를 변경 하거나 쓸 하려고 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="89ad2-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="89ad2-116">`My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad2-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ad2-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="89ad2-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="89ad2-118">문제 해결: 텍스트 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="89ad2-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
