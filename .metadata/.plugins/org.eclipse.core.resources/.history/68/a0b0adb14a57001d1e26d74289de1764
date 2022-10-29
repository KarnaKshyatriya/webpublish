package com.jupiter.controller;

import java.io.IOException;
import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.ResponseEntity;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.servlet.ModelAndView;

import com.jupiter.entity.Jupiter;
import com.jupiter.service.JupiterService;

@RestController
public class JupiterController {

	
	@Autowired
	private JupiterService jsc;
	
	@PostMapping
	public String insert(@RequestBody Jupiter jp)
	{
		try {
			jsc.save(jp);
		
		}
		catch(Exception e){
			System.out.println("No Such Entity");
		}
		return "Success";
		
	}
	
	
	@GetMapping("/all")
	public List<Jupiter> showAll(){
		return jsc.display(); 
	}
	
	@RequestMapping("/users")
	public String home(Model model) {
		model.addAttribute("users", jsc.display());
		return "users";
	}
}
