---
title: 관리형 GDI+에서 이미지 인코더 및 디코더 사용
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: 8cd66f3ce3da462867da9e23c38b3f6d877c058c
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505084"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="61918-102">관리형 GDI+에서 이미지 인코더 및 디코더 사용</span><span class="sxs-lookup"><span data-stu-id="61918-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="61918-103">합니다 <xref:System.Drawing> 네임 스페이스를 제공 합니다 <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 저장 및 이미지 조작을 위한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="61918-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="61918-104">GDI +에서 이미지 인코더를 사용 하 여 디스크에 메모리에서 이미지를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61918-104">By using image encoders in GDI+, you can write images from memory to disk.</span></span> <span data-ttu-id="61918-105">이미지 디코더 GDI +를 사용 하 여 메모리를 디스크에서 이미지를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61918-105">By using image decoders in GDI+, you can load images from disk into memory.</span></span> <span data-ttu-id="61918-106">데이터를 해석 하는 인코더를 <xref:System.Drawing.Image> 또는 <xref:System.Drawing.Bitmap> 지정 된 디스크 파일 형식으로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="61918-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="61918-107">필요한 형식으로 디스크 파일에 데이터를 해석 하는 디코더를 <xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="61918-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="61918-108">GDI + 기본 제공 인코더 및 디코더는 다음 파일 형식을 지 원하는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61918-108">GDI+ has built-in encoders and decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="61918-109">BMP</span><span class="sxs-lookup"><span data-stu-id="61918-109">BMP</span></span>  
  
- <span data-ttu-id="61918-110">GIF</span><span class="sxs-lookup"><span data-stu-id="61918-110">GIF</span></span>  
  
- <span data-ttu-id="61918-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="61918-111">JPEG</span></span>  
  
- <span data-ttu-id="61918-112">PNG</span><span class="sxs-lookup"><span data-stu-id="61918-112">PNG</span></span>  
  
- <span data-ttu-id="61918-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="61918-113">TIFF</span></span>  
  
 <span data-ttu-id="61918-114">GDI +는 다음 파일 형식을 지 원하는 기본 제공 디코더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61918-114">GDI+ also has built-in decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="61918-115">WMF</span><span class="sxs-lookup"><span data-stu-id="61918-115">WMF</span></span>  
  
- <span data-ttu-id="61918-116">EMF</span><span class="sxs-lookup"><span data-stu-id="61918-116">EMF</span></span>  
  
- <span data-ttu-id="61918-117">ICON</span><span class="sxs-lookup"><span data-stu-id="61918-117">ICON</span></span>  
  
 <span data-ttu-id="61918-118">다음 항목에서는 인코더 및 디코더를 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61918-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61918-119">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="61918-119">In This Section</span></span>  
 [<span data-ttu-id="61918-120">방법: 설치 된 인코더 나열</span><span class="sxs-lookup"><span data-stu-id="61918-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="61918-121">컴퓨터에서 사용할 인코더를 나열 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="61918-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="61918-122">방법: 설치 된 디코더 나열</span><span class="sxs-lookup"><span data-stu-id="61918-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="61918-123">컴퓨터에서 사용할 디코더를 나열 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="61918-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="61918-124">방법: 인코더에서 지원 되는 매개 변수 확인</span><span class="sxs-lookup"><span data-stu-id="61918-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="61918-125">나열 하는 방법에 설명 합니다 <xref:System.Drawing.Imaging.EncoderParameters> 인코더에서 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="61918-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="61918-126">방법: BMP 이미지를 PNG 이미지로 변환</span><span class="sxs-lookup"><span data-stu-id="61918-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="61918-127">다른 이미지 형식의 이미지를 저장 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="61918-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="61918-128">방법: JPEG 압축 수준 설정</span><span class="sxs-lookup"><span data-stu-id="61918-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="61918-129">이미지의 품질 수준을 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="61918-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="61918-130">참조</span><span class="sxs-lookup"><span data-stu-id="61918-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="61918-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="61918-131">Related Sections</span></span>  
 [<span data-ttu-id="61918-132">GDI + 관리 코드 정보</span><span class="sxs-lookup"><span data-stu-id="61918-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="61918-133">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="61918-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
