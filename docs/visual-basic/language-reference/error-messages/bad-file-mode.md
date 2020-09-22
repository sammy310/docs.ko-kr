---
title: 파일 모드가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 99b84902ddf032f2ecb6e26400e200bea862dfdf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875143"
---
# <a name="bad-file-mode"></a><span data-ttu-id="5ff74-102">파일 모드가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-102">Bad file mode</span></span>

<span data-ttu-id="5ff74-103">파일 콘텐츠를 조작 하는 데 사용 되는 문은 파일이 열린 모드에 적절 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="5ff74-104">가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-104">Possible causes include:</span></span>  
  
- <span data-ttu-id="5ff74-105">`FilePutObject`또는 `FileGetObject` 문에서 순차 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="5ff74-106">`Print`문이 또는 이외의 액세스 모드로 열린 파일을 지정 합니다 `Output` `Append` .</span><span class="sxs-lookup"><span data-stu-id="5ff74-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="5ff74-107">`Input`문이 다음 이외의 액세스 모드로 열린 파일을 지정 합니다.`Input`</span><span class="sxs-lookup"><span data-stu-id="5ff74-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="5ff74-108">읽기 전용 파일에 쓰려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5ff74-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5ff74-109">To correct this error</span></span>  
  
- <span data-ttu-id="5ff74-110">`FilePutObject`및 `FileGetObject` 에 대해 열려 있는 파일만 참조 하는지 확인 `Random` `Binary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="5ff74-111">`Print` `Output` 또는 액세스 모드에 대해 열려 있는 파일을 지정 해야 합니다 `Append` .</span><span class="sxs-lookup"><span data-stu-id="5ff74-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="5ff74-112">그렇지 않으면 다른 문을 사용 하 여 데이터를 파일에 저장 하거나 적절 한 모드로 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="5ff74-113">`Input`에 대해 열려 있는 파일을 지정 해야 합니다 `Input` .</span><span class="sxs-lookup"><span data-stu-id="5ff74-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="5ff74-114">그렇지 않으면 다른 문을 사용 하 여 데이터를 파일에 저장 하거나 적절 한 모드로 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="5ff74-115">읽기 전용 파일에 쓰는 경우 파일의 읽기/쓰기 상태를 변경 하거나 파일에 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="5ff74-116">`My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff74-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff74-117">참조</span><span class="sxs-lookup"><span data-stu-id="5ff74-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="5ff74-118">문제 해결: 텍스트 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="5ff74-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
