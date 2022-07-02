# Final-assignment
// ignore_for_file: prefer_const_constructors(screen 1)

import 'package:coding_challenge/user_login.dart';
import 'package:flutter/src/foundation/key.dart';
import 'package:flutter/src/widgets/framework.dart';

import 'package:flutter/material.dart';

class getStarted extends StatelessWidget {
  const getStarted({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return SafeArea(
      child: Scaffold(
        appBar: AppBar(title: Text("GET STARTED",style: TextStyle(fontSize: 14),)),
        body: Center(
          child: Column(
            children: [
              SizedBox(
                height: 20,
              ),
              Padding(
                padding: const EdgeInsets.all(8.0),
                child: Container(
                  child: Text(
                    "TRAINING",
                    style: TextStyle(fontSize: 58, color: Colors.purple),
                  ),
                ),
              ),
              SizedBox(
                height: 20,
              ),
              Padding(
                padding: const EdgeInsets.all(8.0),
                child: Container(
                  child: Image(
                      image: NetworkImage(
                          "https://toppng.com/uploads/preview/training-png-11553373957geiyxwlzxd.png")),
                ),
              ),
              SizedBox(
                height: 20,
              ),
              Container(
                child: ElevatedButton(
                    style: ElevatedButton.styleFrom(
                      padding: EdgeInsets.symmetric(
                          horizontal: 100.0, vertical: 8.0),
                      shape: StadiumBorder(),
                    ),
                    onPressed: () {
                      Navigator.push(context,
                          MaterialPageRoute(builder: (context) {
                        return user_login();
                      }));
                    },
                    child: Text(
                      "Get Started",
                      style: TextStyle(fontSize: 24,),
                    )),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
// ignore_for_file: prefer_const_literals_to_create_immutables, prefer_const_constructors(screen 2)

import 'package:flutter/material.dart';

class login extends StatefulWidget {
  const login({Key? key}) : super(key: key);

  @override
  State<login> createState() => _loginState();
}

class _loginState extends State<login> {
  TextEditingController name = TextEditingController();
  TextEditingController email = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return SafeArea(
        child: Scaffold(
      body: Padding(
        padding: const EdgeInsets.all(10.0),
        child: Padding(
          padding: const EdgeInsets.only(top: 30, left: 30),
          child: Column(
            children: [
              Text(
                "Login",
                style: TextStyle(
                    fontSize: 40,
                    fontWeight: FontWeight.bold,
                    color: Color.fromARGB(255, 1, 66, 119)),
              ),
              Padding(
                padding: const EdgeInsets.only(top: 20),
                child: TextField(
                  controller: name,
                  decoration: InputDecoration(
                    icon: Icon(
                      Icons.person,
                      color: Colors.black,
                      size: 30,
                    ),
                    hintText: "Student Name ",
                  ),
                  keyboardType: TextInputType.text,
                ),
              ),
              SizedBox(
                height: 20,
              ),
              Padding(
                padding: const EdgeInsets.only(top: 20),
                child: TextField(
                  controller: email,
                  decoration: InputDecoration(
                    icon: Icon(
                      Icons.email,
                      color: Colors.black,
                      size: 30,
                    ),
                    hintText: "Email Id ",
                  ),
                  keyboardType: TextInputType.emailAddress,
                ),
              ),
              SizedBox(
                height: 30,
              ),
              ElevatedButton(
                onPressed: () {},
                child: Text("Login"),
              )
            ],
          ),
        ),
      ),
    ));
  }
}
// ignore_for_file: prefer_const_constructors(screen 3)

import 'package:coding_challenge/training_completion.dart';
import 'package:flutter/src/foundation/key.dart';
import 'package:flutter/src/widgets/framework.dart';

import 'package:flutter/material.dart';

class user_login extends StatefulWidget {
  const user_login({Key? key}) : super(key: key);

  @override
  State<user_login> createState() => _user_loginState();
}

class _user_loginState extends State<user_login> {
  String? _nameError = null;
  TextEditingController _nameController = TextEditingController();
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        body: SafeArea(
            child: Padding(
                padding: const EdgeInsets.all(20.0),
                child: ListView(
                  children: [
                    Container(
                      margin: EdgeInsets.all(10),
                      child: Text(
                        "Login",
                        style: TextStyle(fontSize: 40, color: Colors.blue),
                      ),
                    ),
                    SizedBox(height: 20,),
                    TextField(
                      maxLength: 20, // maximum character it can hold
                      controller: _nameController,
                      decoration: InputDecoration(
                        errorText: _nameError,
                        labelText: "Student name",
                        labelStyle: TextStyle(fontSize: 15),
                        hintText: "Student name",
                        prefixIcon: Icon(Icons.person),
                        border: UnderlineInputBorder(),
                      ),
                    ),
                    SizedBox(
                      height: 10,
                    ),
                    TextField(
                      decoration: InputDecoration(
                        labelText: "Email ID",
                        
                        errorText: _nameError,
                        labelStyle: TextStyle(fontSize: 15,),
                        prefixIcon: Icon(Icons.alternate_email_rounded),
                        hintText: "Email ID",
                        border: UnderlineInputBorder(
                        ),
                      ),
                      // obscureText: _secureText, // for data not to be visible
                    ),
                    SizedBox(height: 50,),
                    Container(
                child: ElevatedButton(
                    style: ElevatedButton.styleFrom(
                      padding: EdgeInsets.symmetric(
                          horizontal: 80.0, vertical: 8.0),
                      shape: StadiumBorder(),
                    ),
                    onPressed: () {
                      Navigator.push(context,
                          MaterialPageRoute(builder: (context) {
                        return training_completion();
                      }));
                    },
                    child: Text(
                      "Login",
                      style: TextStyle(fontSize: 24,),
                    )),
              ),
                  ],
                ))));
  }
}
