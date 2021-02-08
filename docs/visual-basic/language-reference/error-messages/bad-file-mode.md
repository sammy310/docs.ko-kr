---
description: '자세한 정보: 잘못 된 파일 모드'
title: 파일 모드가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: da792407fb37f5c206be7ff39da14d314ef1e2d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797083"
---
# <a name="bad-file-mode"></a><span data-ttu-id="2a9bf-103">파일 모드가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-103">Bad file mode</span></span>

<span data-ttu-id="2a9bf-104">파일 콘텐츠를 조작 하는 데 사용 되는 문은 파일이 열린 모드에 적절 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-104">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="2a9bf-105">가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-105">Possible causes include:</span></span>  
  
- <span data-ttu-id="2a9bf-106">`FilePutObject`또는 `FileGetObject` 문에서 순차 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-106">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="2a9bf-107">`Print`문이 또는 이외의 액세스 모드로 열린 파일을 지정 합니다 `Output` `Append` .</span><span class="sxs-lookup"><span data-stu-id="2a9bf-107">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="2a9bf-108">`Input`문이 다음 이외의 액세스 모드로 열린 파일을 지정 합니다.`Input`</span><span class="sxs-lookup"><span data-stu-id="2a9bf-108">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="2a9bf-109">읽기 전용 파일에 쓰려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-109">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2a9bf-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="2a9bf-110">To correct this error</span></span>  
  
- <span data-ttu-id="2a9bf-111">`FilePutObject`및 `FileGetObject` 에 대해 열려 있는 파일만 참조 하는지 확인 `Random` `Binary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-111">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="2a9bf-112">`Print` `Output` 또는 액세스 모드에 대해 열려 있는 파일을 지정 해야 합니다 `Append` .</span><span class="sxs-lookup"><span data-stu-id="2a9bf-112">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="2a9bf-113">그렇지 않으면 다른 문을 사용 하 여 데이터를 파일에 저장 하거나 적절 한 모드로 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-113">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="2a9bf-114">`Input`에 대해 열려 있는 파일을 지정 해야 합니다 `Input` .</span><span class="sxs-lookup"><span data-stu-id="2a9bf-114">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="2a9bf-115">그렇지 않으면 다른 문을 사용 하 여 데이터를 파일에 저장 하거나 적절 한 모드로 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-115">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="2a9bf-116">읽기 전용 파일에 쓰는 경우 파일의 읽기/쓰기 상태를 변경 하거나 파일에 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-116">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="2a9bf-117">`My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a9bf-117">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9bf-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a9bf-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="2a9bf-119">문제 해결: 텍스트 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="2a9bf-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
