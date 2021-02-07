# Mobile API

The mean URL Https://gymvue.net

1- Login API 

>   - Request
    - Request type -> POST

    - Parameter 
            {
            'userName': string,
            'password': string
            }

>   - Response
      - Success Return 200
           * If Mobile is Verify before
                    {
                      'userId': int,
                      'token': string,
                      'mobile_verificationy': boolean, *True*
                      'gyms_list': object[
                                    {
                                    'gymId':int,
                                    'gym_name': string,
                                    'gym_image':string,
                                    'last_seen': DateTime
                                    }
                                  ],
                      'status': int            
                      }

             * If Mobile Not Verify
                    {
                      'userId': int,
                      'token': string,
                      'mobile_verificationy': boolean, *False*
                      'status': int            
                      }

      - Error Return 
              {
                  'status': int,
                  'message': string
                }

2- Mobile Send Verification OTP API 

>   - Request
    - Request type -> POST

    - Parameter 
            {
            'userId': int,
            'token': string,
            'mobile': string
            }

>   - Response
      - Success Return 200
                    {
                      'status': int,
                    }
      
      - Error Return 
              {
                  'status': int,
                  'message': string
                } 

3- Mobile Confirm Verificationy OTP  API 

>   - Request
    - Request type -> POST

    - Parameter 
            {
            'userId': int,
            'token': string,
            'OTP': string
            }

>   - Response
      - Success Return 200
                    {
                      'status': int,
                      'gyms_list': object[
                                    {
                                    'gymId':int,
                                    'gym_name': string,
                                    'gym_image':string,
                                    'mobile_verificationy': boolean
                                    }
                                  ],
                    }
      
      - Error Return 
              {
                  'status': int,
                  'message': string
                }   

4- Recover Account API 

>   - Request
    - Request type -> POST

    - Parameter 
            {
            'Recover_method': int (1: email, 2: mobile),
            'userName': string,
            }

>   - Response
      - Success Return 200
                    {
                      'status': int,
                      'userId':int
                    }
      
      - Error Return 
              {
                  'status': int,
                  'message': string
                }

5- Recover Account Verification API 

>   - Request
    - Request type -> POST

    - Parameter 
            {
            'userId': int,
            'OTP': string,
            }

>   - Response
      - Success Return 200
                    {
                      'status': int,
                      'token': string
                    }
      
      - Error Return 
              {
                  'status': int,
                  'message': string
                } 

6- Recover Set New Password API 

>   - Request
    - Request type -> PUT

    - Parameter 
            {
            'userId': int,
            'token': string,
            'password': string
            }

>   - Response
      - Success Return 200
                    {
                      'status': int,
                      'token': string,
                      'gyms_list': object[
                                    {
                                    'gymId':int,
                                    'gym_name': string,
                                    'gym_image':string,
                                    'last_seen': dateTime
                                    }
                                  ]
                    }
      
      - Error Return 
              {
                  'status': int,
                  'message': string
                }  

6- Home API 

>   - Request
    - Request type -> POST

    - Parameter 
            {
            'userId': int,
            'gymId': int,
            'token': string
            }

>   - Response
      - Success Return 200
                    {
                      'status': int,
                      'user_name': 'string',
                      'notifications': int,
                      'upcoming': object[
                                      {
                                      'sessionId':int,
                                      'session_type':int,
                                      'session_title': string,
                                      'IsPaid': boolean,
                                      'date': date,
                                      'time': string,
                                      'image': string,
                                      'intro': text,
                                      'trainer_name': string
                                      },
                                    ],
                      'tabs': object[
                                      {
                                      'title':string,
                                      'descriptian':text,
                                      'number': int,
                                      'image': string,
                                      'link': string
                                      },
                                  ]            
                    }
      
      - Error Return 
              {
                  'status': int,
                  'message': string
                }                                                                              