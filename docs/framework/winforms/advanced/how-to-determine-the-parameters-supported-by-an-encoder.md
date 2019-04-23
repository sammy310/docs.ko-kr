---
title: '방법: 인코더에서 지원하는 매개 변수 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 2626eee239d9876125340dd133c5a9b3e45c3d7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204577"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="60b50-102">방법: 인코더에서 지원하는 매개 변수 확인</span><span class="sxs-lookup"><span data-stu-id="60b50-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="60b50-103">품질 및 압축 수준 등의 이미지 매개 변수를 조정할 수 있지만 매개 변수는 지정 된 이미지 인코더가 지 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b50-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="60b50-104">합니다 <xref:System.Drawing.Image> 클래스를 제공 합니다 <xref:System.Drawing.Image.GetEncoderParameterList%2A> 메서드 특정 인코더에 대 한 지원 되는 이미지 매개 변수를 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b50-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="60b50-105">GUID를 사용 하 여 인코더를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b50-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="60b50-106">합니다 <xref:System.Drawing.Image.GetEncoderParameterList%2A> 메서드는 배열을 반환 <xref:System.Drawing.Imaging.EncoderParameter> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="60b50-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60b50-107">예제</span><span class="sxs-lookup"><span data-stu-id="60b50-107">Example</span></span>  
 <span data-ttu-id="60b50-108">다음 예제 코드는 JPEG 인코더에 대 한 지원 되는 매개 변수를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="60b50-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="60b50-109">매개 변수 범주 및 연관 된 Guid의 목록을 사용 하 여는 <xref:System.Drawing.Imaging.Encoder> 클래스 개요 각 매개 변수에 대 한 범주를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b50-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="60b50-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="60b50-110">Compiling the Code</span></span>  
 <span data-ttu-id="60b50-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="60b50-111">This example requires:</span></span>  
  
-   <span data-ttu-id="60b50-112">Windows Forms 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="60b50-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="60b50-113">A <xref:System.Windows.Forms.PaintEventArgs>에서의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다. </span><span class="sxs-lookup"><span data-stu-id="60b50-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b50-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="60b50-114">See also</span></span>

- [<span data-ttu-id="60b50-115">방법: 설치 된 인코더 나열</span><span class="sxs-lookup"><span data-stu-id="60b50-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="60b50-116">비트맵의 유형</span><span class="sxs-lookup"><span data-stu-id="60b50-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="60b50-117">관리되는 GDI+에서 이미지 인코더 및 디코더 사용</span><span class="sxs-lookup"><span data-stu-id="60b50-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
