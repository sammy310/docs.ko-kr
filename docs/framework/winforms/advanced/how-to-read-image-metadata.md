---
title: '방법: 이미지 메타데이터 읽기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: e2b56175e625281a920c390e5feb4238e3cb7f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182518"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="f9370-102">방법: 이미지 메타데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="f9370-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="f9370-103">일부 이미지 파일에는 이미지의 기능을 결정하기 위해 읽을 수 있는 메타데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="f9370-104">예를 들어 디지털 사진에는 이미지를 캡처하는 데 사용되는 카메라의 확인 및 모델을 결정하기 위해 읽을 수 있는 메타데이터가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="f9370-105">GDI+를 사용하면 기존 메타데이터를 읽을 수 있으며 이미지 파일에 새 메타데이터를 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="f9370-106">GDI+는 개체에 개별 메타데이터를 저장합니다. <xref:System.Drawing.Imaging.PropertyItem></span><span class="sxs-lookup"><span data-stu-id="f9370-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="f9370-107"><xref:System.Drawing.Image> 개체의 <xref:System.Drawing.Image.PropertyItems%2A> 속성을 읽고 파일에서 모든 메타데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="f9370-108">속성은 <xref:System.Drawing.Image.PropertyItems%2A> 개체의 <xref:System.Drawing.Imaging.PropertyItem> 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="f9370-109"><xref:System.Drawing.Imaging.PropertyItem> 개체에는 다음과 같은 네 `Id` `Value`가지 `Len`속성이 있습니다. `Type`</span><span class="sxs-lookup"><span data-stu-id="f9370-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="f9370-110">Id</span><span class="sxs-lookup"><span data-stu-id="f9370-110">Id</span></span>

<span data-ttu-id="f9370-111">메타데이터 항목을 식별하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="f9370-112">할당할 수 있는 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 일부 값은 다음 표에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="f9370-113">16 진수 값</span><span class="sxs-lookup"><span data-stu-id="f9370-113">Hexadecimal value</span></span>|<span data-ttu-id="f9370-114">Description</span><span class="sxs-lookup"><span data-stu-id="f9370-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="f9370-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="f9370-115">0x0320</span></span><br /><br /> <span data-ttu-id="f9370-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="f9370-116">0x010F</span></span><br /><br /> <span data-ttu-id="f9370-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="f9370-117">0x0110</span></span><br /><br /> <span data-ttu-id="f9370-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="f9370-118">0x9003</span></span><br /><br /> <span data-ttu-id="f9370-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="f9370-119">0x829A</span></span><br /><br /> <span data-ttu-id="f9370-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="f9370-120">0x5090</span></span><br /><br /> <span data-ttu-id="f9370-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="f9370-121">0x5091</span></span>|<span data-ttu-id="f9370-122">이미지 제목</span><span class="sxs-lookup"><span data-stu-id="f9370-122">Image title</span></span><br /><br /> <span data-ttu-id="f9370-123">장비 제조업체</span><span class="sxs-lookup"><span data-stu-id="f9370-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="f9370-124">장비 모델</span><span class="sxs-lookup"><span data-stu-id="f9370-124">Equipment model</span></span><br /><br /> <span data-ttu-id="f9370-125">엑시프티오리지널</span><span class="sxs-lookup"><span data-stu-id="f9370-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="f9370-126">노출 시간 엑시프</span><span class="sxs-lookup"><span data-stu-id="f9370-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="f9370-127">휘도 테이블</span><span class="sxs-lookup"><span data-stu-id="f9370-127">Luminance table</span></span><br /><br /> <span data-ttu-id="f9370-128">크로도도 테이블</span><span class="sxs-lookup"><span data-stu-id="f9370-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="f9370-129">값</span><span class="sxs-lookup"><span data-stu-id="f9370-129">Value</span></span>

<span data-ttu-id="f9370-130">값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-130">An array of values.</span></span> <span data-ttu-id="f9370-131">값의 형식은 속성에 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="f9370-132">Len</span><span class="sxs-lookup"><span data-stu-id="f9370-132">Len</span></span>

<span data-ttu-id="f9370-133"><xref:System.Drawing.Imaging.PropertyItem.Value%2A> 속성이 가리키는 값 배열의 길이(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="f9370-134">Type</span><span class="sxs-lookup"><span data-stu-id="f9370-134">Type</span></span>

<span data-ttu-id="f9370-135">속성이 가리키는 배열의 값의 데이터 `Value` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="f9370-136">`Type` 속성 값으로 표시된 형식은 다음 표에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="f9370-137">숫자 값</span><span class="sxs-lookup"><span data-stu-id="f9370-137">Numeric value</span></span>|<span data-ttu-id="f9370-138">Description</span><span class="sxs-lookup"><span data-stu-id="f9370-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="f9370-139">1</span><span class="sxs-lookup"><span data-stu-id="f9370-139">1</span></span>|<span data-ttu-id="f9370-140">`Byte`</span><span class="sxs-lookup"><span data-stu-id="f9370-140">A `Byte`</span></span>|
|<span data-ttu-id="f9370-141">2</span><span class="sxs-lookup"><span data-stu-id="f9370-141">2</span></span>|<span data-ttu-id="f9370-142">ASCII로 인코딩된 개체의 `Byte` 배열</span><span class="sxs-lookup"><span data-stu-id="f9370-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="f9370-143">3</span><span class="sxs-lookup"><span data-stu-id="f9370-143">3</span></span>|<span data-ttu-id="f9370-144">16비트 정수</span><span class="sxs-lookup"><span data-stu-id="f9370-144">A 16-bit integer</span></span>|
|<span data-ttu-id="f9370-145">4</span><span class="sxs-lookup"><span data-stu-id="f9370-145">4</span></span>|<span data-ttu-id="f9370-146">32비트 정수</span><span class="sxs-lookup"><span data-stu-id="f9370-146">A 32-bit integer</span></span>|
|<span data-ttu-id="f9370-147">5</span><span class="sxs-lookup"><span data-stu-id="f9370-147">5</span></span>|<span data-ttu-id="f9370-148">합리적인 숫자를 `Byte` 나타내는 두 개체의 배열</span><span class="sxs-lookup"><span data-stu-id="f9370-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="f9370-149">6</span><span class="sxs-lookup"><span data-stu-id="f9370-149">6</span></span>|<span data-ttu-id="f9370-150">사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="f9370-150">Not used</span></span>|
|<span data-ttu-id="f9370-151">7</span><span class="sxs-lookup"><span data-stu-id="f9370-151">7</span></span>|<span data-ttu-id="f9370-152">정의되지 않음</span><span class="sxs-lookup"><span data-stu-id="f9370-152">Undefined</span></span>|
|<span data-ttu-id="f9370-153">8</span><span class="sxs-lookup"><span data-stu-id="f9370-153">8</span></span>|<span data-ttu-id="f9370-154">사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="f9370-154">Not used</span></span>|
|<span data-ttu-id="f9370-155">9</span><span class="sxs-lookup"><span data-stu-id="f9370-155">9</span></span>|`SLong`|
|<span data-ttu-id="f9370-156">10</span><span class="sxs-lookup"><span data-stu-id="f9370-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="f9370-157">예제</span><span class="sxs-lookup"><span data-stu-id="f9370-157">Example</span></span>
  
<span data-ttu-id="f9370-158">다음 코드 예제에서는 파일에 `FakePhoto.jpg`7개의 메타데이터를 읽고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="f9370-159">목록의 두 번째 (인덱스 1) <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 속성 항목에는 0x010F(장비 제조업체) 및 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2(ASCII 인코딩된 바이트 배열)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="f9370-160">코드 예제에는 해당 속성 항목의 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="f9370-161">코드는 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-161">The code produces output similar to the following:</span></span>

```output
 Property Item 0
  
 id: 0x320
  
 type: 2

 length: 16 bytes
  
 Property Item 1
  
 id: 0x10f
  
 type: 2
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```

## <a name="compiling-the-code"></a><span data-ttu-id="f9370-162">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f9370-162">Compiling the Code</span></span>

<span data-ttu-id="f9370-163">앞의 예제는 Windows Forms와 함께 사용하도록 <xref:System.Windows.Forms.PaintEventArgs> `e`설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 이 요구사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f9370-164">폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리하고 이 코드를 페인트 이벤트 처리기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="f9370-165">시스템에서 유효한 `FakePhoto.jpg` 이미지 이름과 경로로 바꾸고 네임스페이스를 `System.Drawing.Imaging` 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9370-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9370-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9370-166">See also</span></span>

- [<span data-ttu-id="f9370-167">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="f9370-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="f9370-168">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="f9370-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
