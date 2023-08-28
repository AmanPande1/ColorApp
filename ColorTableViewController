//
//  ColorTableViewController.swift
//  ColorApp
//
//  Created by Aman pande on 07/05/23.
//

import UIKit

class ColorTableViewController: UIViewController {

    var color : [UIColor] = []
    override func viewDidLoad() {
        super.viewDidLoad()

        // Do any additional setup after loading the view.
        addRandomColors()
    }
    
    func addRandomColors(){
        for _ in 0..<50{
            color.append(CreateRamdomColor())
        }
    }

    func CreateRamdomColor()-> UIColor{
        
        let randomColor = UIColor(red: CGFloat.random(in: 0...1),
                                  green: CGFloat.random(in: 0...1),
                                  blue: CGFloat.random(in: 0...1),
                                  alpha: 1)
        return randomColor
    }

}

extension ColorTableViewController : UITableViewDelegate ,UITableViewDataSource{
    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return color.count
    }
    
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = tableView.dequeueReusableCell(withIdentifier: "ColorCell")
        let color = color[indexPath.row]
        cell?.backgroundColor = color
        return  cell!
    }
    
    func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
        let color = color[indexPath.row]
        var storyBoard = UIStoryboard(name: "Main", bundle: nil)
        var SecondB = storyBoard.instantiateViewController(withIdentifier: "colorDetailsVC") as! colorDetailsViewController
        SecondB.color = color
        self.navigationController?.pushViewController(SecondB, animated: true)
    }
}
