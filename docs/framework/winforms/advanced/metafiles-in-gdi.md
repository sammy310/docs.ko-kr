---
title: GDI+의 메타파일
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504592"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="49a19-102">GDI+의 메타파일</span><span class="sxs-lookup"><span data-stu-id="49a19-102">Metafiles in GDI+</span></span>
<span data-ttu-id="49a19-103">GDI + 제공은 <xref:System.Drawing.Imaging.Metafile> 클래스를 기록 하 고 메타 파일을 표시할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="49a19-104">벡터 이미지 라고도 불리는 메타 파일 이미지 그리기 명령 및 설정의 시퀀스로 저장 되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="49a19-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="49a19-105">명령 및 설정에 기록를 <xref:System.Drawing.Imaging.Metafile> 개체를 메모리에 저장 하거나 파일 또는 스트림에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="49a19-106">메타 파일 형식</span><span class="sxs-lookup"><span data-stu-id="49a19-106">Metafile Formats</span></span>  
 <span data-ttu-id="49a19-107">GDI +에서는 다음 형식으로 저장 된 메타 파일을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="49a19-108">Windows 메타 파일 (WMF)</span><span class="sxs-lookup"><span data-stu-id="49a19-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="49a19-109">EMF(확장 메타파일)</span><span class="sxs-lookup"><span data-stu-id="49a19-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="49a19-110">EMF+</span><span class="sxs-lookup"><span data-stu-id="49a19-110">EMF+</span></span>  
  
 <span data-ttu-id="49a19-111">GDI +를 기록할 수 메타 파일 EMF, EMF + 형식으로 있지만 WMF 형식에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="49a19-112">EMF +는 GDI + 레코드를 저장할 수 있는 EMF 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="49a19-113">EMF + 형식에 두 가지 변형이 있습니다. EMF +만 및 EMF + 복합 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="49a19-114">EMF + 전용 메타 파일에는 GDI + 레코드만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="49a19-115">GDI는 아니라 GDI +에서 이러한 메타 파일을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="49a19-116">EMF + 복합 메타 파일 GDI 및 GDI + 레코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="49a19-117">EMF + 복합 메타 파일의 각 GDI + 레코드를 대체 GDI 레코드를 이룹니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="49a19-118">이러한 메타 파일은 GDI 또는 GDI +에서 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="49a19-119">다음 예제에서는 이전에 파일로 저장 된 메타 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a19-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="49a19-120">메타 파일에서 왼쪽 위 모퉁이 표시 됩니다 (100, 100).</span><span class="sxs-lookup"><span data-stu-id="49a19-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="49a19-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="49a19-121">See also</span></span>

- [<span data-ttu-id="49a19-122">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="49a19-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
