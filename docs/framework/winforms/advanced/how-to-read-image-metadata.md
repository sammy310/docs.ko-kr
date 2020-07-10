---
title: '방법: 이미지 메타데이터 읽기'
desription: Learn how to read the Windows Forms PropertyItems property of an Image object to retrieve all the metadata from a file.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 814cb17feba1e1e3a42b2bc403b0b4c828caf90e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174668"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="1d225-102">방법: 이미지 메타데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="1d225-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="1d225-103">일부 이미지 파일에는 이미지의 기능을 확인 하기 위해 읽을 수 있는 메타 데이터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="1d225-104">예를 들어 디지털 사진은 이미지를 캡처하는 데 사용 되는 카메라의 제조업체 및 모델을 결정 하기 위해 읽을 수 있는 메타 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="1d225-105">GDI +를 사용 하면 기존 메타 데이터를 읽을 수 있으며 이미지 파일에 새 메타 데이터를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="1d225-106">GDI +는 개체에 메타 데이터의 개별 부분을 저장 <xref:System.Drawing.Imaging.PropertyItem> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="1d225-107"><xref:System.Drawing.Image.PropertyItems%2A>개체의 속성을 읽어서 <xref:System.Drawing.Image> 파일에서 모든 메타 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="1d225-108"><xref:System.Drawing.Image.PropertyItems%2A>속성은 개체의 배열을 반환 합니다 <xref:System.Drawing.Imaging.PropertyItem> .</span><span class="sxs-lookup"><span data-stu-id="1d225-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="1d225-109">개체에는 <xref:System.Drawing.Imaging.PropertyItem> ,, 및의 네 가지 속성이 있습니다 `Id` `Value` `Len` `Type` .</span><span class="sxs-lookup"><span data-stu-id="1d225-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="1d225-110">Id</span><span class="sxs-lookup"><span data-stu-id="1d225-110">Id</span></span>

<span data-ttu-id="1d225-111">메타 데이터 항목을 식별 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="1d225-112">에 할당할 수 있는 일부 값 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="1d225-113">16 진수 값</span><span class="sxs-lookup"><span data-stu-id="1d225-113">Hexadecimal value</span></span>|<span data-ttu-id="1d225-114">설명</span><span class="sxs-lookup"><span data-stu-id="1d225-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="1d225-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="1d225-115">0x0320</span></span><br /><br /> <span data-ttu-id="1d225-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="1d225-116">0x010F</span></span><br /><br /> <span data-ttu-id="1d225-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="1d225-117">0x0110</span></span><br /><br /> <span data-ttu-id="1d225-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="1d225-118">0x9003</span></span><br /><br /> <span data-ttu-id="1d225-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="1d225-119">0x829A</span></span><br /><br /> <span data-ttu-id="1d225-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="1d225-120">0x5090</span></span><br /><br /> <span data-ttu-id="1d225-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="1d225-121">0x5091</span></span>|<span data-ttu-id="1d225-122">이미지 제목</span><span class="sxs-lookup"><span data-stu-id="1d225-122">Image title</span></span><br /><br /> <span data-ttu-id="1d225-123">장비 제조업체</span><span class="sxs-lookup"><span data-stu-id="1d225-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="1d225-124">장비 모델</span><span class="sxs-lookup"><span data-stu-id="1d225-124">Equipment model</span></span><br /><br /> <span data-ttu-id="1d225-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="1d225-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="1d225-126">Exif 노출 시간</span><span class="sxs-lookup"><span data-stu-id="1d225-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="1d225-127">광도 표</span><span class="sxs-lookup"><span data-stu-id="1d225-127">Luminance table</span></span><br /><br /> <span data-ttu-id="1d225-128">색차 테이블</span><span class="sxs-lookup"><span data-stu-id="1d225-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="1d225-129">값</span><span class="sxs-lookup"><span data-stu-id="1d225-129">Value</span></span>

<span data-ttu-id="1d225-130">값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-130">An array of values.</span></span> <span data-ttu-id="1d225-131">값의 형식은 속성에 따라 결정 됩니다 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> .</span><span class="sxs-lookup"><span data-stu-id="1d225-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="1d225-132">Len</span><span class="sxs-lookup"><span data-stu-id="1d225-132">Len</span></span>

<span data-ttu-id="1d225-133">속성이 가리키는 값 배열의 길이 (바이트)입니다 <xref:System.Drawing.Imaging.PropertyItem.Value%2A> .</span><span class="sxs-lookup"><span data-stu-id="1d225-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="1d225-134">형식</span><span class="sxs-lookup"><span data-stu-id="1d225-134">Type</span></span>

<span data-ttu-id="1d225-135">속성이 가리키는 배열에 있는 값의 데이터 형식입니다 `Value` .</span><span class="sxs-lookup"><span data-stu-id="1d225-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="1d225-136">속성 값으로 표시 되는 형식은 `Type` 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="1d225-137">숫자 값</span><span class="sxs-lookup"><span data-stu-id="1d225-137">Numeric value</span></span>|<span data-ttu-id="1d225-138">설명</span><span class="sxs-lookup"><span data-stu-id="1d225-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="1d225-139">1</span><span class="sxs-lookup"><span data-stu-id="1d225-139">1</span></span>|<span data-ttu-id="1d225-140">`Byte`</span><span class="sxs-lookup"><span data-stu-id="1d225-140">A `Byte`</span></span>|
|<span data-ttu-id="1d225-141">2</span><span class="sxs-lookup"><span data-stu-id="1d225-141">2</span></span>|<span data-ttu-id="1d225-142">`Byte`ASCII로 인코딩된 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="1d225-143">3</span><span class="sxs-lookup"><span data-stu-id="1d225-143">3</span></span>|<span data-ttu-id="1d225-144">16 비트 정수</span><span class="sxs-lookup"><span data-stu-id="1d225-144">A 16-bit integer</span></span>|
|<span data-ttu-id="1d225-145">4</span><span class="sxs-lookup"><span data-stu-id="1d225-145">4</span></span>|<span data-ttu-id="1d225-146">32 비트 정수</span><span class="sxs-lookup"><span data-stu-id="1d225-146">A 32-bit integer</span></span>|
|<span data-ttu-id="1d225-147">5</span><span class="sxs-lookup"><span data-stu-id="1d225-147">5</span></span>|<span data-ttu-id="1d225-148">유리수를 나타내는 두 개체의 배열입니다. `Byte`</span><span class="sxs-lookup"><span data-stu-id="1d225-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="1d225-149">6</span><span class="sxs-lookup"><span data-stu-id="1d225-149">6</span></span>|<span data-ttu-id="1d225-150">사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="1d225-150">Not used</span></span>|
|<span data-ttu-id="1d225-151">7</span><span class="sxs-lookup"><span data-stu-id="1d225-151">7</span></span>|<span data-ttu-id="1d225-152">Undefined</span><span class="sxs-lookup"><span data-stu-id="1d225-152">Undefined</span></span>|
|<span data-ttu-id="1d225-153">8</span><span class="sxs-lookup"><span data-stu-id="1d225-153">8</span></span>|<span data-ttu-id="1d225-154">사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="1d225-154">Not used</span></span>|
|<span data-ttu-id="1d225-155">9</span><span class="sxs-lookup"><span data-stu-id="1d225-155">9</span></span>|`SLong`|
|<span data-ttu-id="1d225-156">10</span><span class="sxs-lookup"><span data-stu-id="1d225-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="1d225-157">예제</span><span class="sxs-lookup"><span data-stu-id="1d225-157">Example</span></span>
  
<span data-ttu-id="1d225-158">다음 코드 예제에서는 파일의 7 개 부분으로 된 메타 데이터를 읽고 표시 합니다 `FakePhoto.jpg` .</span><span class="sxs-lookup"><span data-stu-id="1d225-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="1d225-159">목록의 두 번째 (인덱스 1) 속성 항목에는 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010f (장비 제조업체)와 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII로 인코딩된 바이트 배열)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="1d225-160">코드 예제에서는 해당 속성 항목의 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="1d225-161">코드는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-161">The code produces output similar to the following:</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="1d225-162">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1d225-162">Compiling the Code</span></span>

<span data-ttu-id="1d225-163">위의 예제는 Windows Forms와 함께 사용 하도록 설계 되었으며 <xref:System.Windows.Forms.PaintEventArgs> `e` 이벤트 처리기의 매개 변수인가 필요 합니다 <xref:System.Windows.Forms.Control.Paint> .</span><span class="sxs-lookup"><span data-stu-id="1d225-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="1d225-164">폼의 이벤트를 처리 <xref:System.Windows.Forms.Control.Paint> 하 고이 코드를 paint 이벤트 처리기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1d225-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="1d225-165">를 `FakePhoto.jpg` 시스템에서 올바른 이미지 이름 및 경로로 바꾸고 네임 스페이스를 가져와야 합니다 `System.Drawing.Imaging` .</span><span class="sxs-lookup"><span data-stu-id="1d225-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d225-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d225-166">See also</span></span>

- [<span data-ttu-id="1d225-167">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="1d225-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="1d225-168">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="1d225-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
