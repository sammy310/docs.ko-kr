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
ms.openlocfilehash: cd3b636f8f0058d4a8eacc656f95d5f46b8967e2
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040745"
---
# <a name="how-to-read-image-metadata"></a>방법: 이미지 메타데이터 읽기

일부 이미지 파일에는 이미지의 기능을 확인 하기 위해 읽을 수 있는 메타 데이터가 포함 되어 있습니다. 예를 들어 디지털 사진은 이미지를 캡처하는 데 사용 되는 카메라의 제조업체 및 모델을 결정 하기 위해 읽을 수 있는 메타 데이터를 포함할 수 있습니다. GDI +를 사용 하면 기존 메타 데이터를 읽을 수 있으며 이미지 파일에 새 메타 데이터를 작성할 수도 있습니다.

GDI +는 <xref:System.Drawing.Imaging.PropertyItem> 개체에 메타 데이터의 개별 부분을 저장 합니다. <xref:System.Drawing.Image> 개체의 <xref:System.Drawing.Image.PropertyItems%2A> 속성을 읽어서 파일에서 모든 메타 데이터를 검색할 수 있습니다. <xref:System.Drawing.Image.PropertyItems%2A> 속성은 <xref:System.Drawing.Imaging.PropertyItem> 개체의 배열을 반환 합니다.

<xref:System.Drawing.Imaging.PropertyItem> 개체에는 `Id`, `Value`, `Len`및 `Type`의 네 가지 속성이 있습니다.

## <a name="id"></a>ID

메타 데이터 항목을 식별 하는 태그입니다. <xref:System.Drawing.Imaging.PropertyItem.Id%2A>에 할당할 수 있는 일부 값은 다음 표에 나와 있습니다.

|16 진수 값|설명|
|-----------------------|-----------------|
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|이미지 제목<br /><br /> 장비 제조업체<br /><br /> 장비 모델<br /><br /> ExifDTOriginal<br /><br /> Exif 노출 시간<br /><br /> 광도 표<br /><br /> 색차 테이블|

## <a name="value"></a>값

값의 배열입니다. 값의 형식은 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 속성에 의해 결정 됩니다.

## <a name="len"></a>Len

<xref:System.Drawing.Imaging.PropertyItem.Value%2A> 속성이 가리키는 값 배열의 길이 (바이트)입니다.

## <a name="type"></a>Type

`Value` 속성이 가리키는 배열에 있는 값의 데이터 형식입니다. `Type` 속성 값으로 표시 되는 형식은 다음 표에 나와 있습니다.

|숫자 값|설명|
|-------------------|-----------------|
|1|`Byte`|
|2|ASCII로 인코딩된 `Byte` 개체의 배열입니다.|
|3|16 비트 정수|
|4|32 비트 정수|
|5|유리수를 나타내는 두 `Byte` 개체의 배열입니다.|
|6|사용되지 않음|
|7|Undefined|
|8|사용되지 않음|
|10|`SLong`|
|10|`SRational`|

## <a name="example"></a>예제
  
다음 코드 예제에서는 파일 `FakePhoto.jpg`에서 7 개의 메타 데이터를 읽고 표시 합니다. 목록의 두 번째 (인덱스 1) 속성 항목에는 0x010F (장비 제조업체)와 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII로 인코딩된 바이트 배열) <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 있습니다. 코드 예제에서는 해당 속성 항목의 값을 표시 합니다.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

코드는 다음과 유사한 출력을 생성 합니다.

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

## <a name="compiling-the-code"></a>코드 컴파일

위의 예제는 Windows Forms와 함께 사용 하도록 설계 되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`필요 합니다. 양식의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리 하 고이 코드를 paint 이벤트 처리기에 붙여넣습니다. `FakePhoto.jpg`를 시스템에서 올바른 이미지 이름 및 경로로 바꾸고 `System.Drawing.Imaging` 네임 스페이스를 가져와야 합니다.

## <a name="see-also"></a>참조

- [이미지, 비트맵 및 메타파일](images-bitmaps-and-metafiles.md)
- [이미지, 비트맵, 아이콘 및 메타파일 사용](working-with-images-bitmaps-icons-and-metafiles.md)
