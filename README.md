# RestAPITask
onsdag

Opgave 2:
endpoint: https://api.dropboxapi.com/2/files/create_folder_v2

{
    "autorename": false,
    "path": "/TestMappe"
}

Path er det som navngiver mappen, man kan lave undermapper ved at lave mappe/undermappe/undermappemappe.
Det svar man får tilbage er:

{
    "metadata": {
        "name": "Mappe2",
        "path_lower": "/mappe2",
        "path_display": "/Mappe2",
        "id": "id:hTGCb9bguXYAAAAAAAAADA"
    }
}

Som forklare at mappen er blevet lavet

Opgave 3:
For at få info om en mappe, har jeg valgt at bruge meta data
endpoint: https://api.dropboxapi.com/2/files/get_metadata

{
    "include_deleted": false,
    "include_has_explicit_shared_members": false,
    "include_media_info": false,
    "path": "/Homework/math"
}

Og retur kommer der en masse metadata fra DB

Opgave 4:
Endpoint: https://content.dropboxapi.com/2/files/upload

content type laves om til application/octet-stream, ellers kan man ikke uploade filer.

Herefter indsættes
{
    "autorename": false,
    "mode": "add",
    "mute": false,
    "path": "/Homework/math/Matrices.txt",
    "strict_conflict": false
}

Også kommer følgende retur
{
    "name": "tester.txt",
    "path_lower": "/testmappe/tester.txt",
    "path_display": "/TestMappe/tester.txt",
    "id": "id:hTGCb9bguXYAAAAAAAAADg",
    "client_modified": "2023-09-06T08:16:15Z",
    "server_modified": "2023-09-06T08:16:15Z",
    "rev": "01604ac5b7b58aa000000010d00ed81",
    "size": 138,
    "is_downloadable": true,
    "content_hash": "897613a5651c68f7fc49cbfe9206d4f1a072cf05b5936a1f5276a370aaa12876"
}

Opgave 5:

Endpoint: 
https://api.dropboxapi.com/2/file_requests/delete

Parameter: {

    "ids": [
        "oaCAVmEyrqYnkZX9955Y",
        "BaZmehYoXMPtaRmfTbSG"
    ]
}

DeleteFileRequestArgs argument der bruges til at delete.


Opgave 7:

Endpoint: https://api.dropboxapi.com/2/files/search_v2

{
    "match_field_options": {
        "include_highlights": false
    },
    "options": {
        "file_status": "active",
        "filename_only": false,
        "max_results": 20,
        "path": "/Folder"
    },
    "query": "test"
}


Query er det jeg søger efter, i dette tilfældde test.

Retur ok

