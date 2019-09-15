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
ms.openlocfilehash: 8294bc6596c408160a50d9d7d5e6154f66025c73
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988564"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="de2e3-102">방법: 이미지 메타데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="de2e3-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="de2e3-103">일부 이미지 파일에는 이미지의 기능을 확인 하기 위해 읽을 수 있는 메타 데이터가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="de2e3-104">예를 들어 디지털 사진은 이미지를 캡처하는 데 사용 되는 카메라의 제조업체 및 모델을 결정 하기 위해 읽을 수 있는 메타 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="de2e3-105">GDI +를 사용 하면 기존 메타 데이터를 읽을 수 있으며 이미지 파일에 새 메타 데이터를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 <span data-ttu-id="de2e3-106">Gdi +는 <xref:System.Drawing.Imaging.PropertyItem> 개체에 메타 데이터의 개별 부분을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="de2e3-107">개체의 속성<xref:System.Drawing.Image.PropertyItems%2A> 을 읽어서 파일에서 모든 메타 데이터를 검색할 수 있습니다. <xref:System.Drawing.Image></span><span class="sxs-lookup"><span data-stu-id="de2e3-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="de2e3-108">속성 <xref:System.Drawing.Image.PropertyItems%2A> 은 개체의 <xref:System.Drawing.Imaging.PropertyItem> 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="de2e3-109">개체에`Id`는, `Value` ,및`Type`의 네 가지 속성이 있습니다. `Len` <xref:System.Drawing.Imaging.PropertyItem></span><span class="sxs-lookup"><span data-stu-id="de2e3-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="de2e3-110">ID</span><span class="sxs-lookup"><span data-stu-id="de2e3-110">Id</span></span>  
 <span data-ttu-id="de2e3-111">메타 데이터 항목을 식별 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="de2e3-112">에 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 할당할 수 있는 일부 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="de2e3-113">16 진수 값</span><span class="sxs-lookup"><span data-stu-id="de2e3-113">Hexadecimal value</span></span>|<span data-ttu-id="de2e3-114">설명</span><span class="sxs-lookup"><span data-stu-id="de2e3-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="de2e3-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="de2e3-115">0x0320</span></span><br /><br /> <span data-ttu-id="de2e3-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="de2e3-116">0x010F</span></span><br /><br /> <span data-ttu-id="de2e3-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="de2e3-117">0x0110</span></span><br /><br /> <span data-ttu-id="de2e3-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="de2e3-118">0x9003</span></span><br /><br /> <span data-ttu-id="de2e3-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="de2e3-119">0x829A</span></span><br /><br /> <span data-ttu-id="de2e3-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="de2e3-120">0x5090</span></span><br /><br /> <span data-ttu-id="de2e3-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="de2e3-121">0x5091</span></span>|<span data-ttu-id="de2e3-122">이미지 제목</span><span class="sxs-lookup"><span data-stu-id="de2e3-122">Image title</span></span><br /><br /> <span data-ttu-id="de2e3-123">장비 제조업체</span><span class="sxs-lookup"><span data-stu-id="de2e3-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="de2e3-124">장비 모델</span><span class="sxs-lookup"><span data-stu-id="de2e3-124">Equipment model</span></span><br /><br /> <span data-ttu-id="de2e3-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="de2e3-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="de2e3-126">Exif 노출 시간</span><span class="sxs-lookup"><span data-stu-id="de2e3-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="de2e3-127">광도 표</span><span class="sxs-lookup"><span data-stu-id="de2e3-127">Luminance table</span></span><br /><br /> <span data-ttu-id="de2e3-128">색차 테이블</span><span class="sxs-lookup"><span data-stu-id="de2e3-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="de2e3-129">값</span><span class="sxs-lookup"><span data-stu-id="de2e3-129">Value</span></span>  
 <span data-ttu-id="de2e3-130">값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-130">An array of values.</span></span> <span data-ttu-id="de2e3-131">값의 형식은 속성에 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="de2e3-132">Len</span><span class="sxs-lookup"><span data-stu-id="de2e3-132">Len</span></span>  
 <span data-ttu-id="de2e3-133"><xref:System.Drawing.Imaging.PropertyItem.Value%2A> 속성이 가리키는 값 배열의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="de2e3-134">형식</span><span class="sxs-lookup"><span data-stu-id="de2e3-134">Type</span></span>  
 <span data-ttu-id="de2e3-135">`Value` 속성이 가리키는 배열에 있는 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="de2e3-136">`Type` 속성 값으로 표시 되는 형식은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="de2e3-137">숫자 값</span><span class="sxs-lookup"><span data-stu-id="de2e3-137">Numeric value</span></span>|<span data-ttu-id="de2e3-138">Description</span><span class="sxs-lookup"><span data-stu-id="de2e3-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="de2e3-139">1</span><span class="sxs-lookup"><span data-stu-id="de2e3-139">1</span></span>|<span data-ttu-id="de2e3-140">`Byte`</span><span class="sxs-lookup"><span data-stu-id="de2e3-140">A `Byte`</span></span>|  
|<span data-ttu-id="de2e3-141">2</span><span class="sxs-lookup"><span data-stu-id="de2e3-141">2</span></span>|<span data-ttu-id="de2e3-142">ASCII로 인코딩된 `Byte` 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="de2e3-143">3</span><span class="sxs-lookup"><span data-stu-id="de2e3-143">3</span></span>|<span data-ttu-id="de2e3-144">16 비트 정수</span><span class="sxs-lookup"><span data-stu-id="de2e3-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="de2e3-145">4</span><span class="sxs-lookup"><span data-stu-id="de2e3-145">4</span></span>|<span data-ttu-id="de2e3-146">32 비트 정수</span><span class="sxs-lookup"><span data-stu-id="de2e3-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="de2e3-147">5</span><span class="sxs-lookup"><span data-stu-id="de2e3-147">5</span></span>|<span data-ttu-id="de2e3-148">유리수를 나타내는 두 `Byte` 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="de2e3-149">6</span><span class="sxs-lookup"><span data-stu-id="de2e3-149">6</span></span>|<span data-ttu-id="de2e3-150">사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="de2e3-150">Not used</span></span>|  
|<span data-ttu-id="de2e3-151">7</span><span class="sxs-lookup"><span data-stu-id="de2e3-151">7</span></span>|<span data-ttu-id="de2e3-152">Undefined</span><span class="sxs-lookup"><span data-stu-id="de2e3-152">Undefined</span></span>|  
|<span data-ttu-id="de2e3-153">8</span><span class="sxs-lookup"><span data-stu-id="de2e3-153">8</span></span>|<span data-ttu-id="de2e3-154">사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="de2e3-154">Not used</span></span>|  
|<span data-ttu-id="de2e3-155">9</span><span class="sxs-lookup"><span data-stu-id="de2e3-155">9</span></span>|`SLong`|  
|<span data-ttu-id="de2e3-156">10</span><span class="sxs-lookup"><span data-stu-id="de2e3-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="de2e3-157">예제</span><span class="sxs-lookup"><span data-stu-id="de2e3-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="de2e3-158">설명</span><span class="sxs-lookup"><span data-stu-id="de2e3-158">Description</span></span>  
 <span data-ttu-id="de2e3-159">다음 코드 예제에서는 파일 `FakePhoto.jpg`의 7 개 부분으로 된 메타 데이터를 읽고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="de2e3-160">목록의 두 번째 (인덱스 1) 속성 항목에는 0x010f (장비 제조업체)와 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII로 인코딩된 바이트 배열)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="de2e3-161">코드 예제에서는 해당 속성 항목의 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="de2e3-162">코드는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-162">The code produces output similar to the following:</span></span>  
 
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
  
### <a name="code"></a><span data-ttu-id="de2e3-163">코드</span><span class="sxs-lookup"><span data-stu-id="de2e3-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de2e3-164">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="de2e3-164">Compiling the Code</span></span>  
 <span data-ttu-id="de2e3-165">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="de2e3-166">폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리 하 고이 코드를 paint 이벤트 처리기에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="de2e3-167">를 시스템에서 `FakePhoto.jpg` 올바른 이미지 이름 및 경로로 바꾸고 네임 스페이스를 `System.Drawing.Imaging` 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de2e3-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2e3-168">참고자료</span><span class="sxs-lookup"><span data-stu-id="de2e3-168">See also</span></span>

- [<span data-ttu-id="de2e3-169">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="de2e3-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="de2e3-170">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="de2e3-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
